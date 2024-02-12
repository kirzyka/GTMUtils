# Variables > Custom JS > Functions > getParentByCSSClass

    function() {
        return function(cssClass) {        
          var getParentByCSSClass = function(el, cssClass) {
              var parent = el.parentElement;
              
              if (!parent) return null;

              var classList = Array.from(parent.classList);

              if (classList.includes(cssClass)) {
                  return parent;
              }

              return getParentByCSSClass(parent, cssClass);
          }

          return getParentByCSSClass({{Click Element}}, cssClass);
        }
    }
