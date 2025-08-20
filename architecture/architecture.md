# General LLM architecture
-The diagram below shows the general architecture of basically all LLM that exist today:

![Output examples](https://raw.githubusercontent.com/Cohegen/deepseek-from-scratch/main/deepseek_assets/Basic-LLM-architecture.webp)

- Think of an LLM as a car engine that takes oil to release energy that is used to drive the car.
- In general we don't know what takes place inside the car engine, since it a bunch of complex processes that take place inside a car engine.
- Similary most of us are unaware of how LLMs like deepseek,chatGPT, claude etc generate text. We are used to giving the model text and it generates texts as an answer. However, have you ever wondered how these models work under the hood. That's what we'll be doing.


## Journey of a Token through and LLM
- To understand how an LLM works let's use the following sentence as our example: "Attention is all you".
- Our task it to predict what word comes after the word "you".
- Before the predicted part let's begin our journey from the beginning from the start. So we give our model our example sentence as input.
- LLMs don't directly process text directly there are crucial process that take place before doing that, they are:
   1. Tokenization : 

```
\documentclass[border=10pt]{standalone}
\usepackage{tikz}
\usetikzlibrary{shapes.geometric, arrows.meta, positioning}
\usepackage{amsmath}

\begin{document}

% Defining styles for the flowchart
\tikzstyle{process} = [rectangle, minimum width=4cm, minimum height=1.2cm, text centered, draw=black, fill=blue!10, rounded corners, font=\small]
\tikzstyle{arrow} = [thick, -Stealth, color=black]

\begin{tikzpicture}[node distance=2.5cm and 3cm, auto]

% Step 1: Original Sentence
\node (sentence) [process] {Sentence: ``Attention is all you''};

% Step 2: Tokenization
\node (tokens) [process, below=of sentence] {Tokens: [``Attention'', ``is'', ``all'', ``you'']};

% Step 3: Token IDs
\node (ids) [process, below=of tokens] {
  \begin{tabular}{c|c}
    \textbf{Token} & \textbf{ID} \\
    \hline
    Attention & 1012 \\
    is & 52 \\
    all & 348 \\
    you & 77 \\
  \end{tabular}
};

% Arrows with labels
\draw [arrow] (sentence) -- node {Tokenization} (tokens);
\draw [arrow] (tokens) -- node {Assign IDs} (ids);

\end{tikzpicture}

\end{document}





