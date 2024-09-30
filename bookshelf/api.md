# Using Lead's API

Lead's API is pretty straight forward.
Here's the standard practice when fetching Lead's API.

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