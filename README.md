# utl-add-a-quarter-circle-arc-to-scatter-plot-using-r-ggplot-graphics
Add a quarter circle arc to scatter plot using r ggplot graphics
    %let pgm=utl-add-a-quarter-circle-arc-to-scatter-plot-using-r-ggplot-graphics ;

    %stop_submission;

    Hi res plot
    https://tinyurl.com/2zetfxmz
    https://github.com/rogerjdeangelis/utl-add-a-quarter-circle-arc-to-scatter-plot-using-r-ggplot-graphics/blob/main/arc.png

    github
    https://tinyurl.com/mryx2346
    https://github.com/rogerjdeangelis/utl-add-a-quarter-circle-arc-to-scatter-plot-using-r-ggplot-graphics

    Add a quarter circle arc to scatter plot using r ggplot graphics

    stackoverflow
    https://tinyurl.com/26f7mb7s
    https://stackoverflow.com/questions/79448975/plotting-points-and-arc-on-same-ggplot

    Solution by
    https://stackoverflow.com/users/2372064/mrflick

    related ggplot repos on end



    /***************************************************************************************************************************/
    /*                                            |                              |                                             */
    /*                     INPUT                  |        PROCESS               |                  OUTPUT                     */
    /*                     =====                  |        ========              |         https://tinyurl.com/2zetfxmz        */
    /*                                            |                              |         ============================        */
    /*                      X                     | %utlfkil(d:/png/arc.png);    |                                             */
    /*    0     0.2    0.4    0.6    0.8     1    |                              |                                             */
    /* Y -+------+------+------+------+------+--Y | %utl_rbeginx;                |   0     0.2    0.4    0.6    0.8     1      */
    /*  |                                      |  | parmcards4;                  |Y -+------+------+------+------+------+-- Y  */
    /* 1+                   X     X            + 1| library(ggplot2)             |  |                                      |   */
    /*  |                                      |  | library(ggforce)             | 1+O OO  OOO          X     X            + 1 */
    /*  |            X                         |  | library(haven)               |  |         OOO OO                       |   */
    /*  |                           X          |  | source("c:/oto/fn_tosas9x.R")|  |            X   OOO                   |   */
    /* 8+                 X    X        X      +.8| have<-read_sas(              |  |                   OOO     X          |   */
    /*  |                                      |  |  "d:/sd1/have.sas7bdat")     |.8+                 X   OX        X      +.8 */
    /*  |                                      |  | print(have)                  |  |                        OO            |   */
    /*  |                   X                  |  | str(have)                    |  |                          O           |   */
    /* 6+                                      +.6| png("d:/png/arc.png")        |  |                   X        O         |   */
    /*  |                          X           |  | ggplot(have, aes(x=X,y=Y)) + |.6+                             OO       +.6 */
    /*  |                  X                   |  |   geom_point(size = 3) +     |  |                          X   O       |   */
    /*  |  X       X           X            X  |  |   geom_arc(                  |  |                  X            OO     |   */
    /* 4+                                      +.4|     aes(x0 = 0, y0 = 0,      |  |  X       X           X         OO X  |   */
    /*  |                        X             |  |         r = 1,               |.4+                                 O    +.4 */
    /*  |                                      |  |         start = 0,           |  |                        X         O   |   */
    /*  |                        X             |  |         end = pi / 2),       |  |                                   O  |   */
    /* 2+                          X           +.2|     color = "red",           |  |                        X          O  |   */
    /*  |                                      |  |     size=1,inherit.aes=FALSE |.2+                          X        O  +.2 */
    /*  |                                      |  |   )                          |  | https://tinyurl.com/2zetfxmz       O |   */
    /*  |             X                        |  | dev.off()                    |  |                                    O |   */
    /* 0+                    XX                + 0| ;;;;                         |  |             X                      O |   */
    /*  |                                      |  | %utl_rendx;                  | 0+                    XX              O + 0 */
    /*  --+------+------+------+------+------+--  |                              |  |                                    O |   */
    /*    0     0.2    0.4    0.6    0.8     1    | proc print data=sd1.want;    |  -+-------+------+------+------+------+--   */
    /*                     X                      | run;quit;                    |    0     0.2    0.4    0.6    0.8     1     */
    /*                                            |                              |                     X                       */
    /* options validvarname=upcase;               |                              |                                             */
    /* libname sd1 "d:/sd1";                      |                              |                                             */
    /* data sd1.have ;                            |                              |                                             */
    /*   input x  y @@;;                          |                              |                                             */
    /* cards4;                                    |                              |                                             */
    /* 0.72 0.19 0.47 0.82 0.51 0.63 0.48 0.51    |                              |                                             */
    /* 0.97 0.43 0.66 0.25 0.69 0.99 0.33 0.05    |                              |                                             */
    /* 0.25 0.44 0.60 0.43 0.66 0.37 0.53 0.01    |                              |                                             */
    /* 0.73 0.85 0.02 0.44 0.71 0.55 0.85 0.82    |                              |                                             */
    /* 0.57 0.01 0.61 0.82 0.51 0.98 0.30 0.88    |                              |                                             */
    /* ;;;;                                       |                              |                                             */
    /* run;quit;                                  |                              |                                             */
    /*                                            |                              |                                             */
    /***************************************************************************************************************************/

    /*                   _
    (_)_ __  _ __  _   _| |_
    | | `_ \| `_ \| | | | __|
    | | | | | |_) | |_| | |_
    |_|_| |_| .__/ \__,_|\__|
            |_|
    */


    options validvarname=upcase;
    libname sd1 "d:/sd1";
    data sd1.have ;
      input x  y @@;;
    cards4;
    0.72 0.19 0.47 0.82 0.51 0.63 0.48 0.51
    0.97 0.43 0.66 0.25 0.69 0.99 0.33 0.05
    0.25 0.44 0.60 0.43 0.66 0.37 0.53 0.01
    0.73 0.85 0.02 0.44 0.71 0.55 0.85 0.82
    0.57 0.01 0.61 0.82 0.51 0.98 0.30 0.88
    ;;;;
    run;quit;

    options ls=64 ps=32;
    proc plot data=sd1.have(rename=y=y12345678901234567890);
      plot y12345678901234567890*x='X'
      /haxis=0 to 1 by .2 vaxis=0 to 1 by .2 box;
    run;quit;


    /***************************************************************************************************************************/
    /*                                                                                                                         */
    /*                       X                                                                                                 */
    /*     0     0.2    0.4    0.6    0.8     1             X       Y                                                          */
    /*  Y -+------+------+------+------+------+--Y                                                                             */
    /*   |                                      |         0.72    0.19                                                         */
    /*  1+                   X     X            + 1       0.47    0.82                                                         */
    /*   |                                      |         0.51    0.63                                                         */
    /*   |            X                         |         0.48    0.51                                                         */
    /*   |                           X          |         0.97    0.43                                                         */
    /*  8+                 X    X        X      +.8       0.66    0.25                                                         */
    /*   |                                      |         0.69    0.99                                                         */
    /*   |                                      |         0.33    0.05                                                         */
    /*   |                   X                  |         0.25    0.44                                                         */
    /*  6+                                      +.6       0.60    0.43                                                         */
    /*   |                          X           |         0.66    0.37                                                         */
    /*   |                  X                   |         0.53    0.01                                                         */
    /*   |  X       X           X            X  |         0.73    0.85                                                         */
    /*  4+                                      +.4       0.02    0.44                                                         */
    /*   |                        X             |         0.71    0.55                                                         */
    /*   |                                      |         0.85    0.82                                                         */
    /*   |                        X             |         0.57    0.01                                                         */
    /*  2+                          X           +.2       0.61    0.82                                                         */
    /*   |                                      |         0.51    0.98                                                         */
    /*   |                                      |         0.30    0.88                                                         */
    /*   |             X                        |                                                                              */
    /*  0+                    XX                + 0                                                                            */
    /*   |                                      |                                                                              */
    /*   --+------+------+------+------+------+--                                                                              */
    /*     0     0.2    0.4    0.6    0.8     1                                                                                */
    /*                      X                                                                                                  */
    /*                                                                                                                         */
    /***************************************************************************************************************************/
    /*
     _ __  _ __ ___   ___ ___  ___ ___
    | `_ \| `__/ _ \ / __/ _ \/ __/ __|
    | |_) | | | (_) | (_|  __/\__ \__ \
    | .__/|_|  \___/ \___\___||___/___/
    |_|
    */

    %utlfkil(d:/png/arc.png);

    %utl_rbeginx;
    parmcards4;
    library(ggplot2)
    library(ggforce)
    library(haven)
    source("c:/oto/fn_tosas9x.R")
    have<-read_sas(
     "d:/sd1/have.sas7bdat")
    print(have)
    str(have)
    png("d:/png/arc.png")
    ggplot(have, aes(x=X,y=Y)) +
      geom_point(size = 3) +
      geom_arc(
        aes(x0 = 0, y0 = 0,
            r = 1,
            start = 0,
            end = pi / 2),
        color = "red",
        size=1,inherit.aes=FALSE
      )
    dev.off()
    ;;;;
    %utl_rendx;

    /*                   _               _       _
      ___ _ __ ___  __ _| |_ ___   _ __ | | ___ | |_
     / __| `__/ _ \/ _` | __/ _ \ | `_ \| |/ _ \| __|
    | (__| | |  __/ (_| | ||  __/ | |_) | | (_) | |_
     \___|_|  \___|\__,_|\__\___| | .__/|_|\___/ \__|
                                  |_|
    */

    options validvarname=upcase;
    libname sd1 "d:/sd1";
    data arc;
      set sd1.have;
      ltr='X';
      output;
      if _n_=20 then do;
         do x=-1 to 1 by .01;
           do y=-1 to 1 by .01;
             ltr='O';
             if .99 < x**2 + y**2 < 1.01 then do;
                if uniform(1234)<.3 then output;
             end;
           end;
         end;
         stop;
      end;
    run;quit;

    options ls=64 ps=32;
    proc plot data=arc(rename=y=y12345678901234567890);
      plot y12345678901234567890*x=' ' $ ltr
      /haxis=0 to 1 by .2 vaxis=0 to 1 by .2 box;
    run;quit;

    /*           _               _
      ___  _   _| |_ _ __  _   _| |_
     / _ \| | | | __| `_ \| | | | __|
    | (_) | |_| | |_| |_) | |_| | |_
     \___/ \__,_|\__| .__/ \__,_|\__|
                    |_|
    */

    /***************************************************************************************************************************/
    /*                                                                                                                         */
    /*  https://tinyurl.com/2zetfxmz                                                                                           */
    /*                    X                                                                                                    */
    /*   0     0.2    0.4    0.6    0.8     1                                                                                  */
    /*Y -+------+------+------+------+------+-- Y                                                                              */
    /*  |                                      |                                                                               */
    /* 1+O OO  OOO          X     X            + 1                                                                             */
    /*  |         OOO OO                       |                                                                               */
    /*  |            X   OOO                   |                                                                               */
    /*  |                   OOO     X          |                                                                               */
    /*.8+                 X   OX        X      +.8                                                                             */
    /*  |                        OO            |                                                                               */
    /*  |                          O           |                                                                               */
    /*  |                   X        O         |                                                                               */
    /*.6+                             OO       +.6                                                                             */
    /*  |                          X   O       |                                                                               */
    /*  |                  X            OO     |                                                                               */
    /*  |  X       X           X         OO X  |                                                                               */
    /*.4+                                 O    +.4                                                                             */
    /*  |                        X         O   |                                                                               */
    /*  |                                   O  |                                                                               */
    /*  |                        X          O  |                                                                               */
    /*.2+                          X        O  +.2                                                                             */
    /*  |                                    O |                                                                               */
    /*  | https://tinyurl.com/2zetfxmz   O     |                                                                               */
    /*  |             X                      O |                                                                               */
    /* 0+                    XX              O + 0                                                                             */
    /*  |                                    O |                                                                               */
    /*  -+-------+------+------+------+------+--                                                                               */
    /*    0     0.2    0.4    0.6    0.8     1                                                                                 */
    /*                     X                                                                                                   */
    /*                                                                                                                         */
    /***************************************************************************************************************************/

    /*        _       _           _                     _       _
     _ __ ___| | __ _| |_ ___  __| |   __ _  __ _ _ __ | | ___ | |_ ___
    | `__/ _ \ |/ _` | __/ _ \/ _` |  / _` |/ _` | `_ \| |/ _ \| __/ __|
    | | |  __/ | (_| | ||  __/ (_| | | (_| | (_| | |_) | | (_) | |_\__ \
    |_|  \___|_|\__,_|\__\___|\__,_|  \__, |\__, | .__/|_|\___/ \__|___/
                                      |___/ |___/|_|
    */

    https://github.com/rogerjdeangelis/utl-create-a-sankey-diagram-using-r-packages-dplyr-ggsankey-and-ggplot2-lie-stacked-bar-chart
    https://github.com/rogerjdeangelis/utl-creating-circular-boxplot-for-circadian-data-r-ggplot-graphics
    https://github.com/rogerjdeangelis/utl-creating-stacked-ascii-line-bar-plots-and-sas-sgplots-and-r-ggplot2
    https://github.com/rogerjdeangelis/utl-drawing-a-world-map-using-the-eckert-projection-ggplot-map-rnaturalearth
    https://github.com/rogerjdeangelis/utl-lattice-plots-six-histograms-in-three-rows-and-two-columns-ggplot-sgpanels-in-sas-wps-and-r
    https://github.com/rogerjdeangelis/utl-overlay-a-small-version-of-a-plot-inside-a-larger-plot-window-within-window-r-ggplot
    https://github.com/rogerjdeangelis/utl-plot-every-column-against-every-other-column-ggplot-ods-wps
    https://github.com/rogerjdeangelis/utl-r-graphics-vs-wps-base-graphics-layering-in-r-versus-procs-in-wps-base-ggplot2
    https://github.com/rogerjdeangelis/utl-spaghetti-plots-in-sas-and-r-ggplot2-sgplot
    https://github.com/rogerjdeangelis/utl-visualizing-regression-differences-when-regressing-y-vs-x-and-x-vs-y-using-sas-r-ggplot

     /*              _
      ___ _ __   __| |
     / _ \ `_ \ / _` |
    |  __/ | | | (_| |
     \___|_| |_|\__,_|

    */
