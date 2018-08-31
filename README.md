# GPSS 2018 : Labs and Resources
---

## Labs

### Notebooks
Notebooks and answers are in the [`lab` directory](./lab). Some changes from last year:

#### Lab 1 [COMPLETE]: Gaussian Process Regression [[blank](http://nbviewer.jupyter.org/github/wilocw/gpss18_resources/blob/master/lab/GPSS%20Lab%201.ipynb), [answers](http://nbviewer.jupyter.org/github/wilocw/gpss18_resources/blob/master/lab/GPSS%20Lab%201%20Answers.ipynb)]
- Support for Python 3.5+ only
    - This is not essential, but notebooks require some adaptation to change
    - Uses Python 3 specific styling, and have made use of `@` for matrix multiplication, amongst others
- Updated examples
    - Changed real-world example from marathon data to Mauna Loa
        - Based on Rich's notebooks
        - Used primarily to demonstrate kernel choice and combinations of kernels
        - Removed the mean function stuff from Rich's examples
        - Motivation: recognisable case study, good examples of different trends, e.g. linear(ish) growth, periodicity, non-linear aspects, Gaussian likelihood
    - Given some more intuitive examples of summing / multiplying kernels
    - Shown how to sample kernels and given examples of different kinds samples before exercise on identifying kernels based on samples
    - Added explicit calculation of GP posterior using GP equations before introducing GPy as a tool
    - Added exercise showing how bad prediction is for extrapolation, and also briefly introduced the concept of incorporating known info into kernel choice (in this case, periodicity), before explicitly doing it in Mauna Loa example
    - Removed the section on Uncertainty propagation
        - Not clear of purpose, documentation lacking
        - Could be moved into a separate notebook as _extra work_
    - Added short 2-D example similar to Rich's
        - Shows using isotropic kernels and mentions ARD parameter
        - Shows using product of two kernels with different active dimensions
- Removed all use of `m.plot()` and GPy's inbuilt plotting tools
    - Provided a transparent and _short_ function for plotting GP posterior given X, mean and covariance matrix
    - Show how to access these directly from model
    - Avoid using GPy plotting because:
        - Not clear what it's actually showing
        - Documentation bad
        - Hard to use in notebooks, no control over plot canvas
        - GPy is not a plotting library, generally not good practise to use it for plotting (imo)
        - Show how to get predictions, and parameters, so it's clear what is actually being plotted
- Rewritten a lot of text for clarity and correctness
    - Lots of incorrect code examples in text had been carried on over years, have confirmed correctness of everything now
- Exercises:
    1. Effects of parameters on (RBF) kernel
    1. Modelling with and validity of combined kernels
    1. Identify the covariance function
    1. Fitting a GP, changing parameters and sampling posterior
    1. Extrapolating with a GP, embedding prior knowledge for a better
    1. Fitting combinations of kernels to the Mauna Loa dataset
    1. Improving the fit

#### Lab 2 : Non-Gaussian likelihoods / classification [[draft](http://nbviewer.jupyter.org/github/wilocw/gpss18_resources/blob/master/lab/GPSS%20Lab%202%20Answers.ipynb)]
- `WIP`
- Non- Gaussian Likelihoods introduction, with Student's t, Bernoulli examples and 2D classification example
- Sparse GPs with small comparative example and longer sparse exercise
- TODO:
  - write short description of SVI for SGPs based on removed example
  - waiting for any response by Zhenwen but will complete over weekend if not

#### Lab 3 : Bayesian optimisation [[blank](http://nbviewer.jupyter.org/github/wilocw/gpss18_resources/blob/master/lab/GPSS%20Lab%203.ipynb), [answers](http://nbviewer.jupyter.org/github/wilocw/gpss18_resources/blob/master/lab/GPSS%20Lab%203%20Answers.ipynb)]
-  Written by Javier
- TODO: 
  - check for bugs, and fix
  - clean up text
  - minor tweaks to format for consistency

---
## Equipment
![setup](recording_setup.svg)

Setup information available as [pdf](recording_setup.pdf), [png](recording_setup.png), and [svg](recording_setup.svg)

### Description
The speaker should have a laptop plugged into an HDMI cable, and powered. Any conversion between display adaptors should be down so that the HDMI cable can be plugged in. Anyone with a non-UK power lead should use the provided conversion adaptor (apparently there's some legality issues here around using standard ones, but I've identified a multi-adaptor that should be fine). The speaker should also be fitted with the microphone and audio transmitter &ndash; this should be battery powered, rather than by mains, due to reported feedback in the audio receiver. The batteries should be changed in the transmitter after _every speaker_, and in the receiver _every day_.

The laptop display is connected via HDMI to the splitter, which needs to be independently powered. It needs to be plugged into the *middle* port, marked "HDMI-IN". One out should be plugged into the projector via HDMI **(I am presuming that an HDMI cable will be provided in the room to connect to the projector)**.

The second output from the splitter should be directly converted to VGA using the non-powered, short HDMI-VGI adaptor. On the other end of the VGA cable, there should be an gender change adaptor, and the _powered_ VGA-HDMI converter to convert back to HDMI. The adaptor is powered via a micro USB port. The reason for the HDMI-VGA-HDMI conversion is to strip the digital signal (by converting to analogue and back again) of any encryption that may prevent us from recording the screen. This is a confirmed issue on laptops running recent versions of macOS, and the VGA conversion is a successful work-around. Conceivably this could be done _before_ the splitter **(is there any known reason to do it a particular way ?, the limitation currently is that we lose sound output from the laptop in the recording, but can pass a digital signal to the projector)**.

The camera is powered by a USB fixed in the handle, with a 1 m extender available. The output from the camera is passed via microHDMI (inside the screen cover), for which we have a microHDMI to HDMI cable. The camera has no memory, and all recording is performed on the recording box, so **don't press record on the camera**. The audio receiver has an aux output which needs to be converted to R/W component. Both the camera output and audio should be plugged into _channel 1_, via HDMI/component respectively. There are two component adaptors provided in the lecture recorder. The output from the splitter should be plugged into _channel 2_ via HDMI. Headphones can be plugged into the front, for the operator to check the quality of audio in the recording.

### Inventory

| # | Item | Notes |
|---|------|-------|
| 1 | Video Camera | Sony HDR-CX240E, needs USB charger |
| 1 | Tripod | |
| 2 | Audio Transmitter / Receiver | Battery powered |
| 1 | Microphone (clip-on) | Aux (in) |
| 1 | Lecture Recorder | PAT done 26/07/18 |
| 1 | DC 19V Adaptor + lead | for recorder|
| 1 | 4-way HDMI splitter | split laptop signal between projector and recorder |
| 1 | DC 5V adaptor | for splitter |
| 6 | USB Flash Drives (2GB) | _need checking_ |
| 20| Batteries (AA) | Checked for charge |


| # | Cable | Lengths | Notes |
|---|-------|---------|-------|
| 2 | microHDMI `[M]` → HDMI `[M]` | 20 cm, 1 m | camera → recorder |
| 1 | USB-A `[F]` → USB-A `[M]` | 1 m | extends camera power cable|
| 2 | aux `[M]` → aux `[M]` | 30 cm, 1.5 m | non-essential |
| 1 | aux `[M]` → component `[M,M]` | 1.5 m | audio receiver → recorder |
| 3 | VGA `[M]` → VGA `[M]` | 1.5 m | used for analogue conversion in VGA/HDMI setup |
| 1 | microUSB `[M]` → USB-A `[M]` | 1 m | to power VGA/HDMI adaptor |
| 2 | HDMI `[M]` → HDMI `[M]` | 2 m, 10 m | laptop → splitter, splitter → recorder (via VGA) |
| 1 | HDMI `[F]` → HDMI `[M]` | 2 m | extender, non-essential|

| # | Adaptors | Notes |
|---|----------|-------|
| 1 | HDMI `[F]` → miniHDMI `[M]` | non-essential |
| 2 | HDMI `[F]` → microHDMI `[M]` | non-essential |
| 1 | HDMI `[M]` → VGA `[F]` | VGA/HDMI conversion |
| 1 | VGA `[F]` → VGA `[F]` | VGA/HDMI conversion |
| 1 | VGA `[M]` → HDMI/aux `[F,F]` | VGA/HDMI conversion, requires power, needs USB charger |
| 2 | USB power chargers | For camera and VGA/HDMI conversion |
| 1 | mini DisplayPort `[M]` → HDMI `[F]` adaptor | Laptop output adaptor | 
| 1 | DisplayPort `[M]` → HDMI `[F]` adaptor | Laptop output adaptor |
| 1 | USB-C `[M]` → HDMI `[F]` adaptor | Laptop output adaptor | 
| 1 | DVI `[M]` → HDMI `[F]` adaptor | Laptop output adaptor | 
| 1 | Power passport | If speaker does not have UK plug | 
| 1 | Headphones | To check recording audio is working | 
| 1 | Laser Pointer | For speakers if necessary | 
| 12 | Assorted Marker Pens | |
| 1 | Multiline power adaptor | For recording setup, can try and get from support (TO GET) | |
---

## Misc.

### Orders

- T-shirts
    - **ORDERED AND RECEIVED**
    - Due 13-16 August
- Branded stationary
    - Pads of paper **ORDERED AND RECEIVED 100**
    - Pens **ORDERED AND RECEIVED 100**
- Lanyards
    - **ORDERED AND RECEIVED**
    - Holds name badge of size : 8.5 x 5.5 cm  / 3.35 x 2.2 inches

