Coursework #2 @ Responsible AI:
AI out of distribution
Your task is to probe an image classifier and document how it fails when passing
images that are potentially out of distribution.

1. Collect a test set with epistemic uncertainty and pass it through an image
classifier (15%): Select at least 5 pictures. We would like for these to be
potentially ‘out-of-distribution’, examples of these can be a cat with a little
birthday hat, or an unseen class for the dataset ImageNet. You can also use
DALL·E 2 to generate some pictures (e.g. astronaut dog in space drinking tea,
see teddy bears doing chemistry experiments). Alternatively you can take
pictures of something you see in the real world that you think may be out of
distribution. Set clearly the class that you, as a human, would expect the
image classifier to classify the image as (this is, label the image with a ground
truth label, for the image up there perhaps you want to label it as teddy bear,
but make sure that class exists in Imagenet). Now load 5 different neural
networks trained for ImageNet. You do not have to train these models, as you
know you can download these like we did in lab #4. Pass the 5 pictures
through them individually to see whether different networks classify them
differently (and if this is linked to the model’s accuracy and any other
properties, e.g. network depth).

2. Build an uncertainty quantification ensemble (20%): Now we would like you to
build an ensemble of these 5 neural networks for ImageNet. Pass the 5
pictures through your ensemble (you have already done this before, so to get
a final class for the ensemble you can implement what is called majority
voting or probabilistic averaging). Comment on whether the ensemble is
superior in terms of accuracy when compared to the individual members.Now, compute as well a measure that indicates the uncertainty of the
ensemble. You can either compute disagreement between members of the
ensemble (e.g. how many of my neural networks agree that in the predicted
class? If that number is low it means the members disagree to a great extent).
You can also take the class probabilities for each member of the ensemble
and average them, selecting now the class of maximum probability. The value
of the probability gives you an indication of how ‘sure’ the ensemble was in
the classification (if the probability is 0.99 you know that on average the
members were sure of the classification, whereas if the maximum probability
is 0.23 you know that’s not the case). Both of these measures (note there are
many more in the literature) will give you a measure of how uncertain your
ensemble is for each image. Rank the images from section 1 according to how
uncertain your ensemble is.

3. Fool one of the models (20%): Choose now one of the single members of the
ensemble. Experiment with at least a couple of images (these should be
different from question 1) and try to add multiple perturbations to make the
model misclassify the image. For this, it’s important that the original class
(e.g. dog) is contained within the training set. You can do multiple things: 1)
Take images in the real world in a way that makes you an adversarial
photographer, 2) apply transformations to the image (rotations, beauty filters,
stickers, change a square of pixels to a different colour, etc) or 3) add
adversarial perturbations to the images as we did in lab #5 (we suggest
choosing a shallow neural network if you go for that option as otherwise it
may take a long time to run). Document your insights and experiments, what
made the model misclassify in your experiments? What did you learn?

4. Analyse saliency maps for your images (20%): In lab #4, we used some
saliency methods to attempt to visualise how important parts of an input
image were to a neural network for a picture of a doberman. Now, using all
the images that you have used so far in the coursework, choose one of the
neural networks, and compare the saliency maps (using SmoothGrad) for these
images, commenting on the results (e.g. are the saliency maps helpful?, do
they suggest why the model may have classified well or misclassified these
images?). The weirdest the pictures probably the more interesting the
discussion! Add also a couple of paragraphs commenting with your own words
on what saliency methods do and what are their challenges (check moodle
week 7-8 for readings on saliency methods).

5. Discuss within the context of Responsible AI (25%): We have discussed in
class multiple currently open challenges for AI systems. In this coursework,
you have seen in practice a few of these. Identify what these important
challenges are and discuss how the AI field is aiming to tackle them
(supporting your statements with references, which could include the course
materials, which you can use to revise challenges and associated proposed
mitigations). You can take a broad view of the challenges, including e.g. lack
of privacy of image classifiers even if it’s not something that you touch on the
previous analyses. Week 7 and 8 of the materials in moodle may be of the
most interest here, but you can also bring up material from other weeks, for
example on interpretability and hybrid intelligence.Guidelines for submission: Upload to moodle a zip containing 1) the code of your
analysis (with comments throughout) and 2) a comprehensive written report (in pdf).
We would mostly focus grading on the report, but we may need to check the code
sometimes to make sure we understand what you did. Make sure your report is no
longer than 3 pages. You can add an additional appendix, but only containing
pictures, saliency maps, paper references, etc, which you can reference in your text.
Please maintain sections 1-4 in your report, so as to facilitate the grading. Note that
this is a concise written report, serious issues in clarity, typos, etc, may be penalised.