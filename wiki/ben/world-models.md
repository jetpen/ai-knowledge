---
title: World Models
author: Ben Eng
---

# World Models


## Evolution of my thoughts on this topic

[2024-05-28](https://x.com/jetpen/status/1817606750205288515)

My thoughts return to question: how can we represent an AST in an encoding that a neural network can do inference on? A generalized AST would provide a way of modeling the world. This would enable accurate reasoning that is not possible with a lexical tokenization of language.

[2024-08-04](https://x.com/jetpen/status/1820107095783448962)

This is why I believe we need to research how to represent an Abstract Syntax Tree as tokens (an AST Node is a token) that a neural network can operate on. I was talking to a friend yesterday about this, and the insight he added was that NN model weights are like a mathematic computation akin to a Fourier transform. This gave me a lot of hope that my idea that an AST Node (as the unit to represent any concept generically) can be encoded as a token (a number). Once we can do this, we can now represent any language, and therefore any mental model of anything in the real world. (Not just tokens as word fragments like the current generation of LLMs.)

[2024-08-25](https://x.com/jetpen/status/1827772190147891323)

Another avenue to explore is to use an initial encoding to determine what kind of model to use. Classify the problem as natural language, lexical, math, logic, programming (each language is distinct), chemistry, etc. Every domain has its own way of modeling the world. Using this classification, parse the information again using that domain-specific model. Now the AI can reason about the problem using an optimal representation.

[2025-10-06](https://x.com/jetpen/status/1975087569080627357)

It might be too divergent from today's neural network paradigm for neurons to represent an AST directly. Now, I believe we don't need to do that, because we don't need to have a metamodel at the neuron level to represent any language. 

We already have several metamodels that today's LLMs can understand well: YAML and JSON. Any domain specific language can be represented in these formats. A world model can be represented as a document in this format according to some schema. 

Perhaps that is how a human brain represents a world model anyway. We have a concept, a document. Concepts have relationships, which are links. We reason based on large collections of tokens together: a set of concepts and their relationships. 

I have no feel for how my human neurons represent primitive data types like numbers. It certainly isn't lexical (string of digits). However, this is where the document format world model is advantageous. The NN doesn't have to take on the burden of having a representation of numbers like a human brain does, because a NN has the advantage of working with adjunct brains through documents. These are programs that do computation precisely, and an AI can make use of it through MCP. 

An AI doesn't need to have an understanding of numbers and math. We have seen how poorly LLMs do math by themselves. An AI merely has to use a MCP server to communicate the document representing the math problem to a math solver (e.g., Maple or Mathematica), and the answer will always come back perfectly solved. The AI's responsibility is only to understand how to formulate the document request and consume the document response. That is a language the LLM can fully understand how to process.

That can be generalized to everything within the scope of computing.

[2026-01-20](https://x.com/jetpen/status/2013630651346432105)

The more that AI coding agents are guided and driven by markdown documents, the more I am convinced that a world model is merely a set of documents. Therefore, it is in a LLM's wheelhouse to comprehend and update documents to maintain its memory durably.

[2026-05-23](https://x.com/jetpen/status/2058180121526149588)

Consider this. No matter how we model things as data structures in memory, we almost always define a serialization format for network transfer or for durable storage. The file format, especially today is almost always preferred to be yaml or json (including variants of these). 

With LLMs trained for coding, tokenization of yaml and json should be pretty good. Harnesses can query against the structure using jq or improvised python. That enables sophisticated reasoning against a model represented in those formats, especially when compliant to a schema, which most APIs would be. 

My hypothesis is that because world models are represented according to some ontology that governs its in-memory structures, its wire protocol for an API, and its file format for durable storage, it would be natural to think that world models are just documents in yaml or json with a schema along with a ontology to describe the meaning in natural language of the classes, properties, relationships, behavior. That means LLMs can reason perfectly well against real world models as documents. 

LLM-based agents will do reasoning with world model documents better as we invent better representations of ontology to drive the reasoning. Today, we have tool names and tool descriptions in MCP, and we have frontmatter in markdown for skills. We need to do more work in this area to make any json schema or yaml schema understandable (semantically) with an ontology.
