---
layout: post
title:  "Tarkov Profile Parsed (ToastedSherpa)"
date:   2024-08-21 17:10:37 +0100
categories: post
---

I want to learn 🐍Python🐍, and following the approach of previous posts, I decided to do a fun project for it.

To find some motivation, I thought it could be a good idea to do something related to the game Escape From Tarkov, for the ones don't know, it's a shooter-looter quite challenging.

# 💡Idea

The problem with this game is that, there are many cheaters. Most of the Discord servers related to this game, I am in, have like a channel dedicated for people to post screenshots of profiles that are suspicious.
The profile gives some statistics about the player, like the number of raids played, or the number of players killed. Here it's an example on how my profile in 0.14 wipe looks like:

![manuelarte profile](/assets/images/toastedsherpa/profile.png)

I thought it could be fun to make a Discord bot that parses that image to extract player's information, in order to check if there is like a way to "identify" patterns in those profiles.

# 👷Implementation

So, basically the profile picture has always the same format. On the left side you have the picture of the player and the name, and in the center and right side you have the achievements and more statistics.
We are going to focus on parsing the left side of the screenshot.

For that we are going to use [OpenCV](https://opencv.org/), to manipulate the image to being able to extract data from it, and [Tesseract](https://github.com/tesseract-ocr/tesseract) (and open-source OCR), to convert the manipulated image to text.


# Parsing The Name
The name is always in the same position, at the bottom of the player's image. So we can crop that part to make it easier for the OCR.
Tesseract has problems to identify characters in a black background, so in order to facilitate that, we are going to make the image black and white, and invert the colours.

![profile names](/assets/images/toastedsherpa/parse_name.png)

This is the code used:

{% highlight python %}
def transform_name_image(cropped_image: cv2.typing.MatLike) -> cv2.typing.MatLike:
    bw_image = cv2.cvtColor(cropped_image, cv2.COLOR_RGB2GRAY)
    return cv2.bitwise_not(bw_image)

def parse_name(image) -> str:
    cropped_image = crop_name(image)
    transformed_image = transform_name_image(cropped_image)
    output = pytesseract.image_to_string(transformed_image)
    return parse_name_output(output)
{% endhighlight %}

With these changes, Tesseract is able to guess the name properly.

![profile levels](/assets/images/toastedsherpa/parse_level.png)

Parsing The Level
Same principle to parse the level, but in this case, we are going to tell Tesseract that it should find only numbers in the parsed image.


# Parsing Extra Info

TODO

# Technologies/Frameworks Used:

+ 🐍 Python
+ 🤖 [DiscordPy](https://discordpy.readthedocs.io/en/stable/)
+ 🖼️ [OpenCV](https://opencv.org/)
+ 👁️ [Tesseract](https://github.com/tesseract-ocr/tesseract)

If you are interested in learning more about this, feel free to contact me. I have a python playground where you can try it out.