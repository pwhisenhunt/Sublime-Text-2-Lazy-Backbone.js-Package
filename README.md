----
# Lazy [Backbone.js](http://backbonejs.org) Sublime Text 2 snippets for tab completion.
----

Created by Phillip Whisenhunt.

Provides JSDoc and non-JSDoc skeleton structures for Backbone.js views, models, collections, routers, and Backbone.js [Layout Manager](https://github.com/tbranyen/backbone.layoutmanager) views, as well as numerous helper snippets for Backbone.js.

Currently only supports JavaScript, but feel free to contribute Coffee Script.

###General

    bsync       - Backbone.sync('${1:method}', ${2:model}, {${3:options}});
    bemulate    - Backbone.emulate${1:HTTP or JSON} = ${2:true or false};
    bfuncjsdoc  - 
    /**
     * ${1:description}
     * @param {${2:param type}} ${3:param name} ${4:param name description}
     * @return {${5:return type}} ${6:return variable} ${7:return variable description}
     */
    ${8:function name}: function(${9:params}) {
        return ${6:return variable};
    },

    bfunc       - 
    // ${1:description}
    ${2:function name}: function(${3:params}) {        
        return ${4:return variable};
    },

    bhnavigate  - Backbone.history.navigate('${1:fragment}', {${2:options}});
    bhstart     - Backbone.history.start({${1:options}});
    bon         - ${1:model or collection}.on('${2:event}', ${3:callback});

###Model
    
    bmdestroy   - ${1:model}.destroy({${2:options}});
    bmfetch     - 
    ${1:model}.fetch({
        success: function(model, response, options) {
            ${2:success}
        },
        error: function(model, xhr, options) {
            ${3:error}    
        }
    });

    bm          - 
    // ${1:description}
    ${2:variable} = Backbone.Model.extend({

        defaults: {
        },

        validate: function(attributes) {

            // if(attributes.end < attributes.start) {
            //    return 'Error!';
            // }
        },

        initialize: function() {
        },

    //    url: '',
    //    urlRoot: ''
    });

    bmjsdoc     -
    ${2:variable} = Backbone.Model.extend(/** @lends ${3:objectcreated}.prototype */{
        /**
         * @class ${3:objectcreated}
         *
         * @author ${4:author}
         * @augments Backbone.Model
         * @requires jQuery
         * @requires Backbone.js
         * @requires Underscore.js
         * @contructs ${3:objectcreated} object
         */
         
        defaults: {
        },

        validate: function(attributes) {

            // if(attributes.end < attributes.start) {
            //    return 'Error!';
            // }
        },

        initialize: function() {
        },

    //    url: '',
    //    urlRoot: ''
    });

    bmsave      - ${1:model}.save({${2:attributes}}, ${3:options});
    bmset       - ${1:model}.set('${2:key}', ${3:value});
    bmsetm      - ${1:model}.set({'${2:key}': ${3:value}});


###View

    bvdevents   - ${1:scope}.delegateEvents({${2:events}});
    bvundevents - ${1:scope}.undelegateEvents();
    bv          -
    // ${1:description}
    ${2:variable} = Backbone.View.extend({

        el: \$('${3:domelement}'),

        template: ${4:template},

        events: {
        },

        initialize: function() {
            _.bind('this', this.render);

            this.${5:collection or model}.on('change', this.render, this);
            // Override what you wish to do with an error!
            this.${5:collection or model}.on('error', function(error) {
                alert('Error found: ' + error);
            });

            this.render();
        },

        render: function() {
            return this;
        }
    });

    blvjsdoc    -
    ${2:variable} = Backbone.View.extend(/** @lends ${3:objectcreated}.prototype */{
        /**
         * @class ${3:objectcreated}
         *
         * @author ${4:author}
         * @augments Backbone.View
         * @requires jQuery
         * @requires Backbone.js
         * @requires Underscore.js
         * @contructs ${3:objectcreated} object
         */
         
        el: \$('${5:domelement}'),

        template: ${6:template},

        events: {
        },

        initialize: function() {
            _.bind('this', this.render);

            this.${7:collection or model}.on('change', this.render, this);
            // Override what you wish to do with an error!
            this.${7:collection or model}.on('error', function(error) {
                alert('Error found: ' + error);
            });

            this.render();
        },

        render: function() {
            return this;
        }
    });

###Layout Manager View

blvjsdoc -
    ${1:variable} = Backbone.View.extend(/** @lends ${2:objectcreated}.prototype */{
        /**
         * @class ${2:objectcreated}
         *
         * @author ${4:author}
         * @augments Backbone.View
         * @requires jQuery
         * @requires Backbone.js
         * @requires Underscore.js
         * @contructs ${2:objectcreated} object
         */
         
        el: \$('${3:domelement}'),

        template: ${4:template},

        events: {
        },

        initialize: function() {
            _.bind('this', this.render);

            this.${5:collection or model}.on('change', this.render, this);
            // Override what you wish to do with an error!
            this.${5:collection or model}.on('error', function(error) {
                alert('Error found: ' + error);
            });
        },

        serialize: function() {
            // replace this with whatever data your template needs!
            // return this.model.toJSON();
        }

        beforeRender: function() {
        },

        afterRender: function() {
        }
    });

    blv -
    // ${1:description}
    ${2:variable} = Backbone.View.extend({

        el: \$('${3:domelement}'),

        template: ${4:template},

        events: {
        },

        initialize: function() {
            _.bind('this', this.render);

            this.${5:collection or model}.on('change', this.render, this);
            // Override what you wish to do with an error!
            this.${5:collection or model}.on('error', function(error) {
                alert('Error found: ' + error);
            });
        },

        serialize: function() {
            // replace this with whatever data your template needs!
            // return this.model.toJSON();
        }

        beforeRender: function() {
        },

        afterRender: function() {
        }
    });

###Collection
    
    bc          - 
    // ${1:description}
    ${2:variable} = Backbone.Collection.extend({

        initialize: function(models, options) {
        },

        model: ${3:name of model},

        url: '${4:url to hit}'
    });

    bcadd       - ${1:collection}.add([${2:models}], {${3:options}});
    bccreate    - ${1:collection}.create({${2:model attributes}}, {${3:options}});
    bcfetch     - 
    ${1:collection}.fetch({
        success: function(collection, response, options) {
            ${2:success}
        },
        error: function(collection, xhr, options) {
            ${3:error}    
        }
    });

    bcjsdoc     - 
    ${1:variable} = Backbone.Collection.extend(/** @lends ${2:objectcreated}.prototype */{
        /**
         * @class ${2:objectcreated}
         *
         * @author ${3:author}
         * @augments Backbone.Collection
         * @requires jQuery
         * @requires Backbone.js
         * @requires Underscore.js
         * @contructs ${2:objectcreated} object
         */
         
        initialize: function(models, options) {
        },

        model: ${4:nameofmodel},

        url: '${5:urltohit}'
    });

    bcremove    - ${1:collection}.remove([${2:models}], {${3:options}});
    bcreset     - ${1:collection}.reset([${2:models}], {${3:options}});

###Router

    brnavigate  - ${1:router}.navigate('${2:fragment}', {${3:options}});
    brnewroute  - '${1:event} ${2:selector}': '${3:function}'
    brroute     - ${1:router}.route('${2:route}', '${3:name}', ${4:callback});
    brjsdoc     -
    ${1:variable} = Backbone.Router.extend(/** @lends ${2:objectcreated}.prototype */{
        /**
         * @class ${2:objectcreated}
         *
         * @author ${4:author}
         * @augments Backbone.Router
         * @requires jQuery
         * @requires Backbone.js
         * @requires Underscore.js
         * @contructs ${2:objectcreated} object
         */
         
        routes: {
            '${3:event} ${4:selector}': '${5:function}'
        },

        initialize: function(options) {
        }
    });
