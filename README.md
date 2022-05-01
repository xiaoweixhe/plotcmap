PLOTCMAP plots a colormapped 2-D or 3-D line that maps the values of another variable onto the colormap on the line.

Specifies LineStyle, Marker, and LineWidth in the same way as plot/plot3.

-------------------------------------------------------------------------

Syntax:

plotcmap(X, Y, cmap, LineValue)

plotcmap(Y, cmap)

plotcmap(X, Y, Z, cmap)

plotcmap(__, LineValue)

plotcmap(__, LineSpec)

plotcmap(__, 'MatchMarkerFaceColor')

plotcmap(ax, __)

h = plotcmap(__)

-------------------------------------------------------------------------

Description:

plotcmap(X, Y, cmap, LineValue):

plots a 2-D line using plot(X, Y) and
                                 creates a colormap based on cmap on the
                                 line which maps the values of LineValue
                                 onto the colormap.
                                 X, Y, and LineValue must be mumeric
                                 vectors with same length.
                                 cmap can be one of the MATLAB predefined
                                 colormap names or an customized N X 3
                                 colormap matirx.
                                 (list of predefined colormap names:
                                 parula, turbo, hsv, hot, cool, spring,
                                 summer, autumn, winter, gray, bone,
                                 copper, pink, jet, lines, colorcube,
                                 prism, flag, white)

plotcmap(X, Y, cmap):

plots a 2-D line using plot(X, Y) and creates a
                      colormap based on cmap on the line without the
                      values of LineValue where plotcmap maps an implicit
                      set of values ranges from 1 to length(X).

plotcmap(__, LineSpec):

plots a colormapped line with specified
                        LineStyle, Marker, and Color. Use of LineSpec is
                        the same as in plot or plot3.
                        e.g., plotcmap(X, Y, cmap, LineValue, '--o')
                        plotcmap(X, Y, cmap, 'LineWidth', 2).
                        Note that plotcmap overwrites the line color
                        property even if it is specified.

plotcmap(__, 'MatchMarkerFaceColor'):

matchs marker face colors of
                                      each marker to their corresponding
                                      LineValue to create filled markers.

plotcmap(Y, cmap, __):

plots a 2-D colormapped line using plot(Y).

plotcmap(X, Y, Z, cmap, __):

plots a 3-D colormapped line using
                             plot3(X, Y, Z).

plotcmap(ax, __):

displays the plot in the target axes. Specify the axes
                  as the first argument in any of the previous syntaxes.
                  Same as plot or plot3.

h = plotcmap(__):

returns an array of Line objects.

-------------------------------------------------------------------------

Examples:

plotcmap(X, Y, parula, LineValue, '--', 'LineWidth', 2):

  plots a 2-D colormapped line that maps the values of vector LineValue
  onto the predefined colormap parula with dashed line style and
  linewidth of 2pt.

plotcmap(X, Y, jet(20), 'o', 'MatchMarkerFaceColor'):

  plots a 2-D colormapped line that maps an implicit set of values ranges
  from 1 to length(X) onto 20 colors of the predefined colormap jet with
  filled circle marker.

plotcmap(ax1, Y, cmap, LineValue):

  plots a 2-D colormapped line on axis ax1 based on an implicit set of
  x-coordinate values ranges from 1 to length(Y) that maps the values of
  vector LineValue onto the customized N X 3 colormap matrix cmap.

h = plotcmap(X, Y, Z, cool, LineValue, ':s', 'MatchMarkerFaceColor'):

  plots a 3-D colormapped line that maps the values of vector LineValue
  onto the predefined colormap cool with dotted line style and filled
  suqare marker, and returns the line handle to h.

=========================================================================

version 1.1.0

  - Added support for using MATLAB predefined colormaps.
  - Updates in the headline description including a few examples.

Xiaowei He

05/01/2022

=========================================================================

version 1.0.0

Xiaowei He

04/24/2022

=========================================================================
