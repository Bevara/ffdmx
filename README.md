# FFDMX
This filter includes all demultiplexers from ffmpeg :
aa                      asf                     data                    fwse                    image_dpx_pipe          image_xwd_pipe          mm                      ogg                     r3d                     smacker                 vividas
aac                     asf_o                   daud                    g722                    image_exr_pipe          ingenient               mmf                     oma                     rawvideo                smjpeg                  vivo
aax                     ass                     dcstr                   g723_1                  image_gem_pipe          ipmovie                 mods                    osq                     realtext                smush                   vmd
ac3                     ast                     derf                    g726                    image_gif_pipe          ipu                     moflex                  paf                     redspark                sol                     vobsub
ac4                     au                      dfa                     g726le                  image_hdr_pipe          ircam                   mov                     pcm_alaw                rka                     sox                     voc
ace                     av1                     dfpwm                   g729                    image_j2k_pipe          iss                     mp3                     pcm_f32be               rl2                     spdif                   vpk
acm                     avi                     dhav                    gdv                     image_jpeg_pipe         iv8                     mpc                     pcm_f32le               rm                      srt                     vplayer
act                     avr                     dirac                   genh                    image_jpegls_pipe       ivf                     mpc8                    pcm_f64be               roq                     stl                     vqf
adf                     avs                     dnxhd                   gif                     image_jpegxl_pipe       ivr                     mpegps                  pcm_f64le               rpl                     str                     vvc
adp                     avs2                    dsf                     gsm                     image_pam_pipe          jacosub                 mpegts                  pcm_mulaw               rsd                     subviewer               w64
ads                     avs3                    dsicin                  gxf                     image_pbm_pipe          jpegxl_anim             mpegtsraw               pcm_s16be               rso                     subviewer1              wady
adx                     bethsoftvid             dss                     h261                    image_pcx_pipe          jv                      mpegvideo               pcm_s16le               rtp                     sup                     wav
aea                     bfi                     dts                     h263                    image_pfm_pipe          kux                     mpjpeg                  pcm_s24be               rtsp                    svag                    wavarc
afc                     bfstm                   dtshd                   h264                    image_pgm_pipe          kvag                    mpl2                    pcm_s24le               s337m                   svs                     wc3
aiff                    bink                    dv                      hca                     image_pgmyuv_pipe       laf                     mpsub                   pcm_s32be               sami                    swf                     webm_dash_manifest
aix                     binka                   dvbsub                  hcom                    image_pgx_pipe          live_flv                msf                     pcm_s32le               sap                     tak                     webvtt
alp                     bintext                 dvbtxt                  hevc                    image_phm_pipe          lmlm4                   msnwc_tcp               pcm_s8                  sbc                     tedcaptions             wsaud
amr                     bit                     dxa                     hls                     image_photocd_pipe      loas                    msp                     pcm_u16be               sbg                     thp                     wsd
amrnb                   bitpacked               ea                      hnm                     image_pictor_pipe       lrc                     mtaf                    pcm_u16le               scc                     threedostr              wsvqa
amrwb                   bmv                     ea_cdata                ico                     image_png_pipe          luodat                  mtv                     pcm_u24be               scd                     tiertexseq              wtv
anm                     boa                     eac3                    idcin                   image_ppm_pipe          lvf                     musx                    pcm_u24le               sdns                    tmv                     wv
apac                    bonk                    epaf                    idf                     image_psd_pipe          lxf                     mv                      pcm_u32be               sdp                     truehd                  wve
apc                     brstm                   evc                     iff                     image_qdraw_pipe        m4v                     mvi                     pcm_u32le               sdr2                    tta                     xa
ape                     c93                     ffmetadata              ifv                     image_qoi_pipe          matroska                mxf                     pcm_u8                  sds                     tty                     xbin
apm                     caf                     filmstrip               ilbc                    image_sgi_pipe          mca                     mxg                     pcm_vidc                sdx                     txd                     xmd
apng                    cavsvideo               fits                    image2                  image_sunrast_pipe      mcc                     nc                      pdv                     segafilm                ty                      xmv
aptx                    cdg                     flac                    image2_alias_pix        image_svg_pipe          mgsts                   nistsphere              pjs                     ser                     usm                     xvag
aptx_hd                 cdxl                    flic                    image2_brender_pix      image_tiff_pipe         microdvd                nsp                     pmp                     sga                     v210                    xwma
aqtitle                 cine                    flv                     image2pipe              image_vbn_pipe          mjpeg                   nsv                     pp_bnk                  shorten                 v210x                   yop
argo_asf                codec2                  fourxm                  image_bmp_pipe          image_webp_pipe         mjpeg_2000              nut                     pva                     siff                    vag                     yuv4mpegpipe
argo_brp                codec2raw               frm                     image_cri_pipe          image_xbm_pipe          mlp                     nuv                     pvf                     simbiosis_imx           vc1
argo_cvg                concat                  fsb                     image_dds_pipe          image_xpm_pipe          mlv                     obu                     qcp                     sln                     vc1t


## Requirements

[CMake](https://cmake.org/) is used as a build system. To install it, follow
[Debian build instructions](developing_in_debian.md).

[Emscripten SDK](https://emscripten.org/) is required for building
WebAssembly artifacts. To install it, follow the
[Download and Install](https://emscripten.org/docs/getting_started/downloads.html)
guide:

```bash
cd $OPT

# Get the emsdk repo.
git clone https://github.com/emscripten-core/emsdk.git

# Enter that directory.
cd emsdk

# Download and install the latest SDK tools.
./emsdk install latest

# Make the "latest" SDK "active" for the current user. (writes ~/.emscripten file)
./emsdk activate latest
```

## Building the accessor

```bash
# Setup EMSDK and other environment variables. In practice EMSDK is set to be
# $OPT/emsdk.
source $OPT/emsdk/emsdk_env.sh

# Assuming you are in the root level of the cloned repo :
emcmake cmake .
emmake make
```

Once built, you can use and distribute avidmx_1.wasm with your universal tags.

## Documentation

For more details, please visit our documentation at https://bevara.com/documentation/develop/.
