
# Create mvn projects
mvn archetype:generate -DinteractiveMode=true
->
groupid: com.reynolds
artifactid: multi-module-parent/multi-module-1/multi-module-2/multi-module-3

## Assign submodules
  <modules>
    <module>../multi-module-1</module>
    <module>../multi-module-2</module>
    <module>../multi-module-3</module>
  </modules>

# Initialise git repos
each project:
git init
git config user.name "L.Reynolds"