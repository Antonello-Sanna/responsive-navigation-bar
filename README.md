# responsive_navigation_bar
A plug and play solution for your navigation bar needs…
it’s fairly simple but is responsive and can have drop downs if required.
The Component should ideally be loaded directly from the Router as shown in the example.

Usage Example:

    import React from 'react'
    import {
      BrowserRouter as Router,
    } from 'react-router-dom'
    
    import NavBarNPM from './NavBarNPM'
    export default ()=> {
        const options = [
          '/',
          'Gallery',
          'Contact'
        ]
        return(
            <Router>
              <div>
                <NavBarNPM 
                  pages      ={options}
                />
                <div>
                  </div>
              </div>
            </Router>
        )
      }
    

The basic navbar without dropdown  can take the following props, only pages is required as a navbar usually requires at least one!


## **Navbar props types:**


    
        background      = string
        pages           = array(required);
        logo            = string
        logoheight      = string
        color           = string
        borderRadius    = string
        imgLogoAlt      = string
        dropdown_color  = string


## **NAVBAR PROPS DEFALT VALUES**


        background              = 'rgba(1,0,0,.9)'
        pages                   = ['/','gallery','contact','about']
        logo                    ='https://assets-cdn.github.com/images/modules/logos_page/GitHub-Mark.png'
        logoheight              ='50px'
        color                   ='white'
        borderRadius            = '30px'
        imgLogoAlt              = 'github'
        dropdown_color          = 'rgba(1,0,0,.9)'


## **USING DROPDOWNS**

To use dropdowns all you have to do is to pass one or more page as an objects inside the pages array instead of a string using the following format.


    { 'THE_NAME_OF_YOUR_PAGE': { dropdown:['dropdown1', 'dropdown2']}


## **DROPDOWN PROPS TYPES**
        dropdown_color          = string
        dropdown_minWidth       = string
        shadows                 = bool
        dropdown_marginTop      = string
        dropItem_margin_bottom  = string


## **DROPDOWN PROPS DEFALT VALUES**
        dropdown_color          = 'rgba(1,0,0,.9)'
        dropdown_minWidth       = '200px'
        shadows                 = false
        dropdown_marginTop      = '10px',
        dropItem_margin_bottom  = '10px'

Example passing all the optional props and also using dropdowns.


    import React from 'react'
    import {
      BrowserRouter as Router,
    } from 'react-router-dom'
    
    import NavBarNPM from './NavBarNPM'
    export default ()=> {
        const options = [
          '/',
          {
            'Products':
          { dropdown:['dropdown1', 'dropdown2']}
          },
          {
            'About us':
            {dropdown:['dropdown1', 'dropdown2']}
          }
        ]
        return(
            <Router>
              <div>
                <NavBarNPM 
                  pages      ={options}     
                  background      = 'rgba(1,0,0,.9)'
                  pages           = {options}
                  logo            = 'https://assets-cdn.github.com/images/modules/logos_page/GitHub-Mark.png';
                  logoheight      = '50px';
                  color           = 'white';
                  borderRadius    = '30px';
                  imgLogoAlt      = 'github logo';
                  dropdown_color  = 'rgba(1,0,0,.9)';
                />
                <div>
                  </div>
              </div>
            </Router>
        )
      }
