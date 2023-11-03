# Verifiable and Provably Secure Machine Unlearning

This is the code repository accompaning our EuroS&P'24 submission *Verifiable and Provably Secure Machine Unlearning*.

> Machine unlearning aims to remove points from the training dataset of a machine learning model after training; for example when a user requests their data to be deleted. While many unlearning methods have been proposed, none of them enable users to audit the procedure. Furthermore, recent work shows a user is unable to verify whether their data was unlearnt from an inspection of the model parameter alone. Rather than reasoning about parameters, we propose to view verifiable unlearning as a security problem. To this end, we present the first cryptographic definition of verifiable unlearning to formally capture the guarantees of an unlearning system. In this framework, the server first computes a proof that the model was trained on a dataset D. Given a user's data point d requested to be deleted, the server updates the model using an unlearning algorithm. It then provides a proof of the correct execution of unlearning and that d not part of D', where D' is the new training dataset. Our framework is generally applicable to different unlearning techniques that we abstract as admissible functions. We instantiate a protocol in the framework, based on cryptographic assumptions, using SNARKs and hash chains. Finally, we implement the protocol for three different unlearning techniques and validate its feasibility for linear regression, logistic regression, and neural networks.

## Evaluation

We implemented our framework based on [CirC](https://github.com/circify/circ/) and [Spartan](https://github.com/microsoft/Spartan). For ease of use, we included a Dockerfile with all necessary tools to reproduce the results from the paper. It can be build via

```
git clone https://github.com/verifiable-unlearning/artifacts.git verifiable-unlearning
cd verifiable-unlearning; ./docker.sh build
```

Beside building, the `docker.sh` script allows to spawn a shell in the container:

```
./docker.sh shell 
```

or run the evaluation:

```
./docker.sh eval 
```
