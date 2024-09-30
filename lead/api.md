# Using Lead's API

Lead's API is pretty straight forward.
Here's the standard practice when fetching Lead's API.

# Installation
Below shows you how to install Lead API into your project.
## Gradle
Add it in your root build.gradle at the end of repositories:
```java
    dependencyResolutionManagement {
        repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
        repositories {
		mavenCentral()
		maven { url 'https://jitpack.io' }
        }
    }
```
Add the dependency
```java
    dependencies {
        implementation 'com.github.Lodestones:Lead:1.0.6'
    }
```
## Maven
Add the JitPack repository to your build file
```xml
    <repositories>
        <repository>
            <id>jitpack.io</id>
            <url>https://jitpack.io</url>
        </repository>
    </repositories>
```
Add the dependency
```xml
    <dependency>
        <groupId>com.github.Lodestones</groupId>
        <artifactId>Lead</artifactId>
        <version>1.0.6</version>
    </dependency>
```

## Calling the Lead API

```java
import to.lodestone.leadapi.LeadAPI;

public class MainPlugin extends JavaPlugin {

    @Override
    public void onEnable() {
        // Enable Logic Here
    }

    @Override
    public void onDisable() {
        // Disable Logic Here
    }

    public ILeadAPI lead() {
        return LeadAPI.getApi();
    }

}
```

## Using the Lead API

Let's create a listener prevents players from hitting their teammates.

```java
import example.project.leadtest.MainPlugin;
import org.bukkit.entity.Player;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import to.lodestone.leadapi.api.ITeam;
import to.lodestone.bookshelfapi.api.util.MiniMessageUtil;

public class ExampleClass implements Listener {

    private final MainPlugin plugin;

    public ExampleClass(MainPlugin plugin) {
        this.plugin = plugin;
    }

    @EventHandler
    public void on(EntityDamageByEntityEvent event) {
        if (event.getDamager() instanceof Player damager) {
            if (event.getEntity() instanceof Player victim) {
                ITeam team = plugin.lead().getTeam(victim.getUniqueId());
                if (team != null && team.containsMember(damager.getUniqueId())) {
                    event.setCancelled(true);
                    damager.sendMessage(MiniMessageUtil.deserialize("<red>You cannot damage your own teammates!</red>"));
                }
            }
        }
    }

}
```