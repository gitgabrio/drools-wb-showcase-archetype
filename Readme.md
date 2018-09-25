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

    mvn clean process-resources -DskipTests compile gwt:run
    
Test in the browser
-------------------

http://localhost:8888/drools-wb-showcase.html

