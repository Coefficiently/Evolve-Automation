## This fork contains multiple forks and changes pulled from:

https://github.com/Vollch/Evolve-Automation

https://github.com/kewne7768/evolve_automation

https://github.com/SkyeAmphi/Evolve-Automation-Skye

## This fork also contains script configurations for different farming setups that are found within the Script Configurations folder

## General Tips

- **Tooltips**: Most script options have tooltips explaining what they do. If you have questions, make sure to read them.
- **Clicks and Performance**: The script tends to perform a lot of clicks. It is highly recommended to enable key multipliers and bind them to Shift, Control, Alt, or Meta keys (in any combination) for best performance.

## Advanced Configuration

- **Ctrl + Click**: Pressing Ctrl and clicking on almost any script option brings up advanced configurations. This allows you to override settings under specific conditions and apply more advanced logic.
    - **Important Note**: Some elements cannot be overridden, including:
        - Triggers (changed with this fork)
        - Evolution queue
        - Log filters
        - Smart powering for interlinked buildings (e.g., transport and bireme)
        - Priorities (draggables, some changed with this fork)
        - The overrides themselves
    - Overrides only affect the script's behavior. The GUI (outside of the overrides modal) will always show the default values and changes.

## AutoMarket, AutoGalaxyMarket, AutoFactory, and AutoMiningDroid

- These systems use weightings and priorities to determine tasks.
    - Resources are split into priority groups.
    - Within each group, resources with the best priority are distributed based on their weights.
    - If there are unused routes/factories/drones, the script moves to the next lower-priority group.
    - **Priority of -1**: This value means "same as current highest." Resources with this priority will always be crafted alongside the highest priority resources, without interrupting them.
    - **Priority of 0**: Resources with 0 priority won't be crafted unless manually prioritized (increasing their priority).
    - **Weighting of 0**: Resources with 0 weighting will never be crafted, regardless of configured priority or prioritization.
- **Global Checkboxes**: AutoMarket and AutoFactory have separate global checkboxes per resource. When disabled (for both buying and selling in AutoMarket), the script won’t touch those resources and will leave them as manually set.

## Mech Lab Numbers

- Added numbers represent:
    - Design Efficiency
    - Real Mech Damage (affected by most factors)
    - Damage Per Used Space
    - For all of these, larger numbers are better.
- **Collectors**: Show their supply collection rate.

## Building/Research Queues and Prioritization

- **Queues, Triggers, and Available Researches**: These prioritize missing resources, overriding other script settings.
    - If you encounter issues with factories producing the wrong resources or market buying not working as expected, you can disable this feature under general settings.
    - Alternatively, adjust the settings of the producing facilities:
        - **0 Weighting**: Resources with 0 weighting won’t be produced, even if the script tries to prioritize them.
        - **Priority -1**: Resources with this priority will always have the highest priority, even if a facility is set to prioritize something else.

## Auto Storage

- **Storage Crates/Containers**: Auto Storage will assign crates/containers to ensure enough storage to build all buildings with Auto Build enabled.
    - If storage grows too high and takes up all crates, you can disable expensive buildings, and Auto Storage will stop fulfilling its demands.
    - To expand storage for manual builds, limit the maximum level of the building to 0. This will keep Auto Build enabled but prevent it from building automatically, allowing you to manually add the required storage.

## Power Management

- **Building Power Order**: The order in which buildings receive power depends on the order in the settings. You can drag and drop to adjust priorities.
- **Filtering**: You can filter buildings based on name, settings, and resource cost, such as:
    - "build==on"
    - "power==off"
    - "weight<100"
    - "soul gem>0"
    - "iron>=1G"
- **Ascension Trigger**: The Ascension Trigger is placed to activate as soon as possible without negatively impacting soldiers or population, and it aims to reduce prestige rewards. However, it can hurt production.
    - If you're planning to ascend at the first opportunity (without planning for pillars, etc.), you may want to enable auto powering.
    - Alternatively, you can delay the ascension until you're ready
