# GruntLearn
First attempts at using grunt.


----------Installing grunt-------------
1. Install node.js to device to implement npm package installer.
2. In cmd at any directory type "install -g grunt-cli", this will install a global version of grunt.
3. Then in specified folder/project directory enter "npm install grunt", u can access file directory by typing cd C:/documents/project.
4. Then to create package.json file for website attributes and dependencies put in cmd "npm init". Fill in all information that is asked for.
5. Now to install grunt package input into cmd "npm install grunt --save-dev" to install grunt officially.
6. Add gruntfile.js manually and add...

      module.exports = function(grunt) {
        //Configure Task(s)
        grunt.initConfig({
          pkg: grunt.file.readJSON('package.json'),
        });

        //Load the plugins
        grunt.loadNpmTasks( );

        //Register task(s)
        grunt.registerTask('default', [ ]);

      };
7. Now grunt setup is complete, you can now move on to adding tasks and plugins.





----------Installing grunt Plugins-------------
1. First you must load your desired plugin by entering "npm install <(grunt-contrib-)plugin-name> --save-dev" to the cmd prompt.
2. Next you must configure the plugin in your gruntfile.js by entering the code/object that can be found from the plugins page, Example...
      uglify: {
        build:{
          src: 'src/js/script.js',
          dest: 'js/script.min.js'
        }
      }
3. Then you must load the plugin in the gruntfile.js by adding "grunt-contrib-uglify" to the loadNpmTasks section.
4. Finally you must register the task by telling what to run when grunt is activated.
5. Then you can run it by typing Grunt in the command prompt, you should end up with your results.


----------Installing grunt Watch-------------
1. To install grunt watch you begin with the installation by typing in cmd "npm install grunt-contrib-watch --save-dev".
2. Now configure the task with the following code...
      watch: {
        js: {
          files: ['src/js/test.js'],
          tasks: ['uglify:dev']
        }
      }
3. Load the plugin with "grunt.loadNpmTasks('grunt-contrib-watch');" in the task loading section of our gruntfile.js.
4. With the watch plugin registering the task is not necessary so from here you can just simply type in cmd "grunt watch" to initialize. 
