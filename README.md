# Neural Device Scanning Research

Resources and research to learn more about how machine learning can be used for device and message scanning.

While device scanning can be done without machine learning, we are heading towards a future where secure enclaves on devices such as phones can be used together with on-device machine learning models to threaten our privacy and security. Apple devices now contain a secretive on-chip neural engine coprocessor which interacts with the Secure Enclave Processor.

Not only are black box machine learning models being frequently used now, but the world is moving towards black box processing units. An arms race has started where tech companies seek to obscure what code is running on our devices and researchers race to reverse engineer to keep them accountable.


## Misc Machine Learning Stuff

- [Training a Classifier – PyTorch](https://pytorch.org/tutorials/beginner/blitz/cifar10_tutorial.html)
- [Building Your First ConvNet – with TensorFlow and Keras](https://blog.floydhub.com/building-your-first-convnet/)
- [Training a neural net to play a video game with a Deep Q Learning agent – PyTorch](https://pytorch.org/tutorials/intermediate/reinforcement_q_learning.html)

## Black Box Models

[Why Are We Using Black Box Models in AI When We Don’t Need To? A Lesson From An Explainable AI Competition | MIT Press](https://hdsr.mitpress.mit.edu/pub/f9kuryi8/release/6)

> In 2018, a landmark challenge in artificial intelligence (AI) took place, namely, the Explainable Machine Learning Challenge. The goal of the competition was to create a complicated black box model for the dataset and explain how it worked. One team did not follow the rules. Instead of sending in a black box, they created a model that was fully interpretable. This leads to the question of whether the real world of machine learning is similar to the Explainable Machine Learning Challenge, where black box models are used even when they are not needed.

> Rudin, C., & Radin, J. (2019). Why Are We Using Black Box Models in AI When We Don’t Need To? A Lesson From An Explainable AI Competition. Harvard Data Science Review, 1(2). https://doi.org/10.1162/99608f92.5a8a3a3d


[Explainable Machine Learning Challenge](https://community.fico.com/s/explainable-machine-learning-challenge)


## Convolutional Neural Network

[A Comprehensive Guide to Convolutional Neural Networks — the ELI5 way | towardsdatascience.com](https://towardsdatascience.com/a-comprehensive-guide-to-convolutional-neural-networks-the-eli5-way-3bd2b1164a53)


[Perceptual image hashing based on a deep convolution neural network for content authentication
](https://www.researchgate.net/publication/327308456_Perceptual_image_hashing_based_on_a_deep_convolution_neural_network_for_content_authentication)

> Jiang, Cuiling. (2018). Perceptual image hashing based on a deep convolution neural network for content authentication. Journal of Electronic Imaging. 27. 1. 10.1117/1.JEI.27.4.043055.




## Perceptual Hashing

Perceptual hashing is the use of an algorithm that produces a snippet or fingerprint of various forms of multimedia.

https://en.wikipedia.org/wiki/Perceptual_hashing

Perceptual hashing can be done on top of a convolutional neural net neural network.

**What is a hash?**

A function that can be used to map data of arbitrary size to data of fixed size.

**Cryptographic hash vs perceptual hashing**

Examples of cryptographic hashes are MD5 and SHA-256. MD5 is considered insecure as collisions can be quickly calculated. SHA-1 is now vulnerable to collisions too. SHA-256, SHA-512, SHA-2, etc are not *currently* vulnerable to collisions.

Bitcoin uses SHA-256 to generate verifiably "random" numbers in a way that requires a predictable amount of CPU effort.

**What is a collision?**

A collision means the same hash value for two different inputs. For simple hash functions it is easy to reach a collision. For example, assume a hash function h(text) sums of all character codes in a text. It will produce the same hash value (collision) for texts holding the same letters in different order, i.e. h('abc') == h('cab') == h('bca'). To avoid collisions, cryptographers have designed collision-resistant hash functions.

> ref: https://wizardforcel.gitbooks.io/practical-cryptography-for-developers-book/content/cryptographic-hash-functions/crypto-hashes-and-collisions.html

### Use Cases

Potential applications include copyright protection, similarity search for media files, or even digital forensics. For example, YouTube could maintain a database of hashes that have been submitted by the major movie producers of movies to which they hold the copyright. If a user then uploads the same video to YouTube, the hash will be almost identical, and it can be flagged as a possible copyright violation. The audio hash could be used to automatically tag MP3 files with proper ID3 information, while the text hash could be used for plagiarism detection.

> ref: https://www.phash.org/


[Evaluating Perceptual Image Hashes at OkCupid](https://tech.okcupid.com/evaluating-perceptual-image-hashes-at-okcupid-e98a3e74aa3a)

> At OkCupid, we sometimes run into users and bots that re-use the same photos we’ve seen before. While sometimes we can simply check if a photo has been seen (and banned) before, we often run into the case where a banned photo has been manipulated slightly — so an exact comparison won’t work.

### Learn How To Do Perceptual Hashing

https://github.com/aetilius/pHash – Open-source perceptual hashing library. No machine learning? Written in C++.

[How to Create a Duplicate Image Detection System | towardsdatascience.com](https://towardsdatascience.com/how-to-create-a-duplicate-image-detection-system-a30f1b68a2e3)

- Using dHash, a difference hash function (Python lib `imagehash`)

Testing image hash functions: https://content-blockchain.org/research/testing-different-image-hash-functions/



## Private Set Intersection

https://decentralizedthoughts.github.io/2020-03-29-private-set-intersection-a-soft-introduction/

PSI can be used with an untrusted third party: also known as server aided PSI.

It is however possible to design a protocol that does not require a third party at all.



## Apple NeuralHash

### Code

**NeuralHash collision**

https://github.com/anishathalye/neural-hash-collider

### Articles

[Apple’s NeuralHash — How it works and how it might be compromised](https://towardsdatascience.com/apples-neuralhash-how-it-works-and-ways-to-break-it-577d1edc9838)



### Papers

[Bugs in our Pockets: The Risks of Client-Side Scanning](https://arxiv.org/abs/2110.07450)

> Abelson, H., Anderson, R., Bellovin, S. M., Benaloh, J., Blaze, M., Callas, J., … Troncoso, C. (2021). Bugs in our Pockets: The Risks of Client-Side Scanning. arXiv [cs.CR]. Opgehaal van http://arxiv.org/abs/2110.07450

### Articles

Leading cryptographers warn the proposed schemes to detect child abuse images are a form of mass surveillance

[Auto-scans of phones would violate data privacy, say security experts | FT](https://www.ft.com/content/64a74bde-4d64-4940-8c03-e01eeecc6e54)
- Refers to study “Bugs in our Pockets: The Risks of Client-Side Scanning”
- https://archive.is/4RXTH


## Processing Units

### Neural Coprocessor

https://medium.com/swlh/apples-m1-secret-coprocessor-6599492fc1e1

AMX reverse engineered: https://gist.github.com/dougallj/7a75a3be1ec69ca550e7c36dc75e0d6f

Apple devices now contain a secret Apple Matrix coprocessor.

**Why is it secret?**

Most likely because ARM are reluctant to extensions to the standard ARM instruction set. They are worried that if custom instructions are widely used it could fragment the ARM ecosystem.

### Secure Enclave

https://www.theiphonewiki.com/wiki/Secure_Enclave_Processor

https://www.blackhat.com/docs/us-16/materials/us-16-Mandt-Demystifying-The-Secure-Enclave-Processor.pdf
