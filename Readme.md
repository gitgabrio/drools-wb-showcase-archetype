Drools WB Showcase Archetype
===============================

Summary
-------
This archetype will create a simple Showcase for a Drools Workbench screen. The showcase will contain the requested screen,  the "Data Object", and the "Package" ones


Create a project
----------------
    mvn archetype:generate \
        -DarchetypeGroupId=org.drools \
        -DarchetypeArtifactId=drools-wb-showcase-archetype \
        -DarchetypeVersion=7.12.0-SNAPSHOT \
        -DgroupId=my.groupid \
        -DartifactId=MyArtifact \
        -Dversion=(parent_version) \
        -DartifactName=(artifact_name) \
        -DartifactDescription=(artifact_description) \
        -DscreenModule=(module_name)
        -DmodulePackage=(package_of_the_module)
        -DbaseModuleName=(module_name_part_common)
        -DarchetypeRepository=http://gitgabrio.github.io/rools-wb-showcase-archetype

Note: The above command will bootstrap a project using the archetype published here: http://gitgabrio.github.io/drools-wb-showcase-archetype

screenModule: e.g. drools-wb-scenario-simulation-editor
modulePackage: e.g. org.drools.workbench.screens.scenariosimulation
baseModuleName: e.g. DroolsWorkbenchScenarioSimulationEditor (common part for both DroolsWorkbenchScenarioSimulationEditorAPI and DroolsWorkbenchScenarioSimulationEditorClient)


Run the project
---------------

Navigate to newly created project directory (my-artifactId) and then run:

    mvn -DskipTests compile gwt:run
    
Test in the browser
-------------------

http://localhost:8080/MyArtifact

Implementation details
----------------------
For the client side the eventbus architecture has been used to allow component decoupling.
 
For the server side the components are managed by the Spring framework.

About the container
-------------------
The application makes use of the new Servlet 3.0 specification, i.e. it does not use web.xml but it is completely managed by annotation. 
The drawback of this approach is that (currently) it does not run inside the Jetty server (embedded with the GWT environment) so Tomcat should be used for development. 
The generated Readme.md contains detailed instructions on how to cope with that.



