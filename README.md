
# **Text generation with an RNN**

This projext demonstrates how to generate text using a character-based RNN. We will work with a Shakespeare dataset. Given a sequence of characters from this data ("Shakespear"), training a model to predict the next character in the sequence. Longer sequences of text can be generated by calling the model repeatedly.

The model consists of the following layers:

- tf.keras.layers.Embedding: The first layer that mapping the numbers of each character to a vector with embedding_dim dimensions
- tf.keras.layers.GRU
- tf.keras.layers.Dense: The output layer, with vocab_size outputs

![](https://github.com/MarwanMohamed95/Text-Generation-using-RNN/blob/main/text_generation_training.png)

#### The prediction loop
The steps to generate the text:

- It Starts by choosing a start string, initializing the RNN state and setting the number of characters to generate.

- Get the prediction distribution of the next character using the start string and the RNN state.

- Then, use a categorical distribution to calculate the index of the predicted character. Use this predicted character as our next input to the model.

- The RNN state returned by the model is fed back into the model so that it now has more context, instead than only one word. After predicting the next word, the modified RNN states are again fed back into the model, which is how it learns as it gets more context from the previously predicted words.

#### Sample output using start token = "ROMEO:" 

ROMEO: Grumio, go you twenty princely general: for this time,
The golden carses for grise and my bring his lady passing breath: the
seven'd with our trobberous death, is dust.
Our ships mistaking to a second cause?

KING RICHARD II:
First, thenefore castle my for getting at your face?
Prepare you, Catesby.
Thou'rt any caust. This is another,
Thou know'st, as now but one, that Henry, for this dire,
And in their gartes shall be come.'

PETRUCHIO:
A deceit brooks, and sullen show
our dustiness spoken:
In all pleased for a little breeling left by the
butt thou wast barrant forbid, come again,
And I'll swear to rsy titles of thy soul!
Councilst Richard, now methld not be brief.

BUCKINGHAM:
Why should be cold, All to pieces: boy, here's none;
Away with her, she could be executine, so ling is done.
The Volick, word if about
To old freedom, rage: let me see thee better
Thus doing the instrument delivers' heirs,
A mark thee chamber-with world!
Fear not, my ass me Swoon;'
And, those Claudio to my wife
