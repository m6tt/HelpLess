![HelpLess logo](http://m6tt.github.com/HelpLess/img/logo.png)

## HelpLess ##

1. What is it?

    HelpLess is a Helper Library for the brilliant LESS dynamic stylesheet language.
    Read more about LESS: http://lesscss.org/
  
    I have tried to make HelpLess as all-encompasing as possible with support for dynamic grids and page starter themes as well as all the css3 features I could think of.
    
    HelpLess has an invisible footprint until you call a mixin so if you import HelpLess but don't use it, it will not increase your compiled file size.

2. Installing

    Clone the repository or download the zip and include helpless in your main style.less file

3. Compatibility

    You will need less.js to compile LESS or one of the other compile tools available. See [lesscss.org](http://lesscss.org) for more details
    
4. Getting Started
    
    **Importing**

        @import 'libs/helpless-x.x.x.less'; // Where x.x.x corresponds to the version number


    **Normalize**
    To add normalize.css to your stylesheet call #hl.normalize() at the top of the document outside of any html elements.
    
        #hl.normalize();
        
        body {
            ...
        }
        
    **Clearfix**
    
        body {
            ...
            
            .ul {
                #hl.clearfix();
                
               li {
                   float: left;
                   ...
               }
            }
        }
    
    
    **Setting up a grid.**
    I will use the following html structure as an example:
    
        <html>
        ...
        <body>
            <div id="main">
                <article>
                    <div class="content">
                        ...
                    </div>
                    <aside>
                        ...
                    </aside>
                </article>
            </div>
        </body>
        </html>
        
    To add my grid to this html I would use:
    
        body {
            ...
            
            #main {
                #hl.grid.960(); // default 960 grid with 16 columns and a 10px gutter
                
                article {
                    #hl.grid.row();
                    
                    .content {
                        #hl.grid.col(10);
                    }
                    
                    aside {
                        #hl.grid.col(6);
                    }
                }
            }
        }
        
        
    **Themes**
    Themes are a way of quickly styling the base elements of your page. They do not add any structural or layout based styling
    
        body {
            #hl.ui.themes.light();
            
            ...
        }
        
        
    **Typography**
    There a number of different helpers for typography. If you want to quickly choose a serif style with the addition of a webfont you would:
    
        body {
            #hl.typo.serif('Sorts Mill Goudy');
            
            ...
        }
        
    or a sans-serif:
    
        body {
            #hl.typo.sans('Droid Sans');
            
            ...
        }
        
        
    **Lists**
    To quickly remove the default bullet styling from a list:
    
        ul {
            #hl.ui.list.subtle();
        }
    
    And a horizontal list, for example if you were creating a site nav that runs along the top of the page
    
        ul {
            #hl.ui.list.horizontal();
        }
       
    
    
    
5. Reference

  ------------------------------------------------------------------------------
    BASICS                     =>    syntax
  ------------------------------------------------------------------------------
    - .reset                   =>    #hl.reset() - call outside of element
    - .normalize               =>    #hl.normalize - call outside of element
    - .clearfix                =>    #hl.clearfix()
    - .centered                =>    #hl.centered(width)
    - .border                  =>    #hl.border(color)
    - .opacity                 =>    #hl.opacity(value)
    - .round-all-corners       =>    #hl.round-all-corners(radius)
    - .rounded-corners         =>    #hl.rounded-corners(topLeft, topRight, bottomRight, bottomLeft)
    - .transition              =>    #hl.transition(property, duration, ease, delay)
    - .drop-shadow             =>    #hl.drop-shadow(x, y, blur, color)
    - .inner-shadow            =>    #hl.inner-shadow(x, y, blur, color)
    - .text-shadow             =>    #hl.text-shadow(x, y, blur, color)
    - .background-gradient     =>    #hl.background-gradient(colorFrom, colorTo, fallbackColor, fallbackImageUrl)
    - .scale                   =>    #hl.scale(amount)
    - .scaleX                  =>    #hl.scaleX(amount)
    - .scaleY                  =>    #hl.scaleY(amount)
    - .rotate                  =>    #hl.rotate(degrees)
    - .rotateX                 =>    #hl.rotateX(degrees)
    - .rotateY                 =>    #hl.rotateY(degrees)
    - .skew                    =>    #hl.skew(angleX, angleY)
    - .skewX                   =>    #hl.skewX(angleX)
    - .skewY                   =>    #hl.skewY(angleY)
    - .translate               =>    #hl.translate(x, y)
    - .translateX              =>    #hl.translateX(x)
    - .translateY              =>    #hl.translateY(y)
    - .matrix                  =>    #hl.matrix(n, n, n, n, n, n)

  ------------------------------------------------------------------------------
    GRID                       =>    syntax
  ------------------------------------------------------------------------------
    - .grid                    =>    namespace, do not call directly, use .make or one of the predefined grid makers
     - .make                   =>    #hl.grid.make(width, colNumber, gutterWidth)
     - .1200                   =>    #hl.grid.1200();
     - .1120                   =>    #hl.grid.1120();
     - .1040                   =>    #hl.grid.1040();
     - .960                    =>    #hl.grid.960();
     - .880                    =>    #hl.grid.880();
     - .800                    =>    #hl.grid.800();
     - .720                    =>    #hl.grid.720();
     - .640                    =>    #hl.grid.640();
     - .560                    =>    #hl.grid.560();
     - .480                    =>    #hl.grid.480();
     - .400                    =>    #hl.grid.400();
     - .320                    =>    #hl.grid.320();
     - .240                    =>    #hl.grid.240();
     - .row                    =>    #hl.grid.row();
     - .col                    =>    #hl.grid.col(colSpan);

  ------------------------------------------------------------------------------
    TYPOGRAPHY
  ------------------------------------------------------------------------------
    - .typo                    =>    namespace, do not call directly
     - .serif                  =>    #hl.typo.serif(webfont-name-optional);
     - .sans                   =>    #hl.typo.sans(webfont-name-optional);
     - .columns                =>    #hl.typo.columns(count, gap)
 
  ------------------------------------------------------------------------------
    IMAGES
  ------------------------------------------------------------------------------
    - .img                     =>    namespace, do not call directly
     - .responsive             =>    #hl.img.responsive();
     - .framed                 =>    #hl.img.framed();

  ------------------------------------------------------------------------------
    USER INTERFACE
  ------------------------------------------------------------------------------
    - .ui                      =>    namespace, do not call directly
     - .themes                 =>    namespace, do not call directly
      - .light                 =>    #hl.ui.themes.light(); - call within <body> element
      - .dark                  =>    #hl.ui.themes.dark(); - call within <body> element
     - .list                   =>    namespace, do not call directly
      - .subtle                =>    #hl.list.subtle(); - call within <ul> element
      - .horizontal            =>    #hl.list.horizontal(); - call within <ul> element

7. Thanks 
   
    Included in HelpLess are two reset mixins:

    Eric Meyer's [html reset](http://meyerweb.com/eric/tools/css/reset/)
    Necolas' [normalize](https://github.com/necolas/normalize.css)

6. License
    
    HelpLess is released under the MIT license.
    
    Meyer Reset: public domain
    Normalize: Public domain
