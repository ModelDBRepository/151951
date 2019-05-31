GCAL: Gain Control, Adaptation, Laterally connected

Simple but robust single-population V1 model orientation map from:

   Jean-Luc R. Stevens, Judith S. Law, Jan Antolik, and James A. Bednar.
   Mechanisms for stable, robust, and adaptive development of orientation
   maps in the primary visual cortex.
   Journal of Neuroscience, 33:15747-15766, 2013.

   Development of orientation maps in ferret and cat primary visual
   cortex (V1) has been shown to be stable, in that the earliest
   measurable maps are similar in form to the eventual adult map,
   robust, in that similar maps develop in both dark rearing and in a
   variety of normal visual environments, and yet adaptive, in that
   the final map pattern reflects the statistics of the specific
   visual environment. How can these three properties be reconciled?
   Using mechanistic models of the development of neural connectivity
   in V1, we show for the first time that realistic stable, robust,
   and adaptive map development can be achieved by including two
   low-level mechanisms originally motivated from single-neuron
   results. Specifically, contrast-gain control in the retinal
   ganglion cells and the lateral geniculate nucleus reduces variation
   in the presynaptic drive due to differences in input patterns,
   while homeostatic plasticity of V1 neuron excitability reduces the
   postsyn- aptic variability in firing rates. Together these two
   mechanisms, thought to be applicable across sensory systems in
   general, lead to biological maps that develop stably and robustly,
   yet adapt to the visual environment. The modeling results suggest
   that topographic map stability is a natural outcome of low-level
   processes of adaptation and normalization. The resulting model is
   more realistic, simpler, and far more robust, and is thus a good
   starting point for future studies of cortical map development.


   @article{Stevens02102013,
      author = {Stevens, Jean-Luc R. and Law, Judith S. and Antolik,
      Jan and Bednar, James A.},
      title = {Mechanisms for Stable, Robust, and Adaptive Development
      of Orientation Maps in the Primary Visual Cortex},
      journal = {The Journal of Neuroscience}
      volume = {33},
      number = {40},
      pages = {15747-15766},
      year = {2013},
      doi = {10.1523/JNEUROSCI.1037-13.2013},
      url = {http://www.jneurosci.org/content/33/40/15747.full}
   }

=================
Running the model
=================

This model may be run with the Topographica simulator as follow:

./topographica -g gcal.ty

A suitable version of the Topographica simulator may be obtained using
git:

git clone https://github.com/ioam/topographica.git
cd topographica
git submodule update --init
git checkout GCALModelDB

After 10000 iterations (~ 15 minutes on a quad-core 3Ghz machine), the
orientation map corresponding to the condition shown in Figure 9F can
be measured (GCAL model at 100% contrast). In the GUI, this may be
viewed by opening the Orientation Preference window (Plots ->
Preference Maps -> Orientation Preference).

The default settings are appropriate for quick simulations, suitable
for regular exploratory work. An exact match to Figure 9E requires a
slower simulation:

./topographica -p cortex_density=98 -p area=1.5 -g gcal.ty

The linear density of cortical units is doubled for a cortical area of
1.5 x 1.5. Making the cortical area 2.25 times larger allows border
effects to be eliminated from the central 1.0 x 1.0 area. With four
times more cortical units due to the higher density, the overall
network is nine times larger.


=================================
Reproducing all published figures
=================================

An IPython Notebook detailing how to reproduce the entire paper
(including all figures and simulations) may be viewed or run from
here:

http://topographica.org/_static/stevens_jn13.html
