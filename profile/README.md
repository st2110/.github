# NMOS and SMPTE ST 2110, in Rust

Everyone who ships something for SMPTE ST 2110 writes the same code first: the
IS-04 resource model, an IS-05 client, mDNS discovery, and then a long tail of
fixes for what real devices actually answer. None of that is anyone's
competitive advantage. It should be written once, in public, and tested against
real boxes.

That is what this organization is for.

## crate-nmos

The protocol layer as a Rust library. IS-04 types validated against the
published AMWA schemas, IS-05 connection management, HTTP clients for both, and
optional mDNS discovery behind a feature flag.

It knows the protocol and nothing else — it holds no state and enforces no
policy, so it fits under a controller, a device, a test harness or a monitoring
agent equally well. Apache-2.0, so it can go into a product.

## jackfield

A controller you can actually run. Point it at a network and it shows the Nodes
it found, what each one exposes, and what is streaming where; then you patch
senders to receivers. One binary, no registry, no configuration file, no
install.

It is meant for the moment when you need to see a plant right now — during
commissioning, on someone else's site, or on a bench with two converters and a
switch. Apache-2.0.

## If you build for 2110

Use the crate; that is what it is there for. And send us what your equipment
answers — we keep device responses as test fixtures, and each one becomes a
regression that cannot come back. Vendors read NMOS slightly differently, and
the only cure is having their real answers in the test suite.

Issues and pull requests are welcome on either repository.
