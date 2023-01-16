# Building-a-neural-network-model-to-identify-three-subatomic-particles
I created a neural network model (two hidden layers, each with 128 neurons and an activation function of sigmoid, epochs = 500 and batch_size=100) using TensorFlow that is able to distinguish between decay modes of the Z boson, the J/psi meson (the ground state of charmonium), and the Y meson, a quarkonium state, with an accuracy of 87%.
The CERN Dataset: I created a neural network model using TensorFlow that is able to distinguish between decay modes of the Z boson, the J/psi meson (the ground state of charmonium), and the Y meson, a quarkonium state, with an accuracy of 87%.

First of all, I would like to explain these particles as follows:

1) Z bosons are fundamental particles responsible for weak force along with W bosons.
2) J/psi meson - the ground state of charmonium - is a subatomic particle, and it is a flavor-neutral meson consisting of a charm quark and a charm antiquark.
3) The ϒ meson is a quarkonium state (i.e. flavorless meson) formed from a bottom quark and its antiparticle.

My research is based on these three particles written as follows (Zmumu & Jpsimumu & Ymumu):

1) Zmumu: An event was selected if there were two muons in the event with pT > 20 GeV and |eta| < 2.1 and the invariant mass of the two muons was > 60 GeV and < 120 GeV.
2) Jpsimumu: An event was selected if there were two muons in the event, both with |eta| < 2.4, at least one muon was a global muon, the invariant mass of the two muons was > 2 GeV and < 5 GeV, and they have opposite-sign charge.
3) Ymumu: An event was selected if there were two muons in the event, both with |eta| < 2.4, at least one muon was a global muon, the invariant mass of the two muons was > 8 GeV and < 12 GeV, and they have opposite-sign charge.

I use three datasets, which are available on the CERN Open Data portal, Zmumu.csv with 10,000 records, Jpsimumu.csv and Ymumu.csv, each of which contains 20,000 records.

The first thing I do is train a simple Neural Network (two hidden layers, each with 128 neurons and an activation function of sigmoid, epochs = 500 and batch_size=100), and then plot accuracy and loss graphs on the training and validation datasets to find a balance between the model that is underfitting and one that is overfitting(or converging), resulting in a model with a good fit.

According to the plot of loss, validation loss is decreasing before the 200th epoch, so the model is underfitting. However, after the 200th epoch, validation loss is increasing, which indicates the model is overfitting. At the 200th epoch, when the model is either perfectly fitted or in a local minimum, the neural network model achieved an accuracy of 87%. I found an optimum where the change in the slope of loss is around the 200th epoch, as shown below. At that point, the training process can be stopped.
