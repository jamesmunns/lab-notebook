# Lore

Funny snippets of history

## Rust

### Load bearing build system nop

This is code from the pre-1.0 version of Rust's build system.

Code [available here](https://github.com/rust-lang/rust/blob/efec34a95a76212b2324d98f3f6d94a1397c2544/mk/prepare.mk#L44-L51).

```makefile
# Copy a dylib or rlib
# $(1) is the filename/libname-glob
#
# XXX: Don't remove the $(nop) command below!
# Yeah, that's right, it's voodoo. Something in the way this macro is being expanded
# causes it to parse incorrectly. Throwing in that empty command seems to fix the
# problem. I'm sorry, just don't remove the $(nop), alright?
define PREPARE_LIB
    $(nop)
    @$(call E, prepare: $(PREPARE_WORKING_DEST_LIB_DIR)/$(1))
    $(Q)LIB_NAME="$(notdir $(lastword $(wildcard $(PREPARE_WORKING_SOURCE_LIB_DIR)/$(1))))"; \
    MATCHES="$(filter-out %$(notdir $(lastword $(wildcard $(PREPARE_WORKING_SOURCE_LIB_DIR)/$(1)))),\
                        $(wildcard $(PREPARE_WORKING_DEST_LIB_DIR)/$(1)))"; \
    if [ -n "$$MATCHES" ]; then                                              \
      echo "warning: one or libraries matching Rust library '$(1)'" &&       \
      echo "  (other than '$$LIB_NAME' itself) already present"     &&       \
      echo "  at destination $(PREPARE_WORKING_DEST_LIB_DIR):"                    &&       \
      echo $$MATCHES ;                                                       \
    fi
    $(Q)$(PREPARE_LIB_CMD) `ls -drt1 $(PREPARE_WORKING_SOURCE_LIB_DIR)/$(1) | tail -1` $(PREPARE_WORKING_DEST_LIB_DIR)/
endef
```

### Bastion of the TurboFish

Code [available here](https://github.com/rust-lang/rust/blob/2155adbc3aeb4b38466a7127a7f4e92a8f8fc4e5/src/test/ui/bastion-of-the-turbofish.rs#L3-L31).

```rust
// Bastion of the Turbofish
// ------------------------
// Beware travellers, lest you venture into waters callous and unforgiving,
// where hope must be abandoned, ere it is cruelly torn from you. For here
// stands the bastion of the Turbofish: an impenetrable fortress holding
// unshaking against those who would dare suggest the supererogation of the
// Turbofish.
//
// Once I was young and foolish and had the impudence to imagine that I could
// shake free from the coils by which that creature had us tightly bound. I
// dared to suggest that there was a better way: a brighter future, in which
// Rustaceans both new and old could be rid of that vile beast. But alas! In
// my foolhardiness my ignorance was unveiled and my dreams were dashed
// unforgivingly against the rock of syntactic ambiguity.
//
// This humble program, small and insignificant though it might seem,
// demonstrates that to which we had previously cast a blind eye: an ambiguity
// in permitting generic arguments to be provided without the consent of the
// Great Turbofish. Should you be so naïve as to try to revolt against its
// mighty clutches, here shall its wrath be indomitably displayed. This
// program must pass for all eternity, fundamentally at odds with an impetuous
// rebellion against the Turbofish.
//
// My heart aches in sorrow, for I know I am defeated. Let this be a warning
// to all those who come after. Here stands the bastion of the Turbofish.

// See https://github.com/rust-lang/rust/pull/53562
// and https://github.com/rust-lang/rfcs/pull/2527
// for context.

fn main() {
    let (oh, woe, is, me) = ("the", "Turbofish", "remains", "undefeated");
    let _: (bool, bool) = (oh<woe, is>(me));
}
```
