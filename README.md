# rede (network)

## introduction

a decentralized alternative for git/github/github pages

## description

every user in the network is also a server. while using the network, the user is
also collaborating in running the network code and distributing the files stored
on it.

the network stores its own code and the adresses of the sub-networks running
directly on it. all users in the network have access to these codes.

the more storage/processing you provide to the network you are part of, the
more storage/processing from it you can use.

every user on the network is considered a sub-network.

every user gains voting power in the network they are part of, time weighted
proportional to how much they contribute in storage/processing to the network
they are using.

new sub-networks can only be added when there is available space/processing
on the network. this means new users can only join a network if there is
available capacity on it.

every sub-network can run its own code as long as it also runs the code of
the network above it. the size of the custom code and the amount of processing
it can use is proportional to how much it contributes to the network it is
part of.

a sub-network that contributes more than 1% of resources to the network above
it can initiate a vote for part of its code to be added to the parent network.
a two-thirds majority is required for approval.

a sub-network that contributes to more than 10% of resources of the network
abote it can initiate a vote to replace a part of the code of the network above
with it's own code. a two-third majority is required for approval.

## root network

provides a storage/hosting service. hosts a root file with the code that
the network runs, a JIT compiler to run it and any additional files the user
wants
