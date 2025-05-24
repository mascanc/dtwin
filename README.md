# Digital Twin for Cybersecurity of the SGAM DER Use Case

The [Smart Grid Reference Architecture (SGAM)](https://energy.ec.europa.eu/document/download/9ddd45d7-52eb-4541-85e4-ea58cfe9089b_en?filename=xpert_group1_reference_architecture.pdf) identifies the _Control Reactive Power of DER Unit_ use case, for monitoring voltage level in distribution grid, controlling reactive power of DER unit, and volt/var control of distribution grid.

The use case is used to shown the SGAM methodology applied to a concrete scenario, involving a SCADA, a Human Machine Interaction interface, and a Distribution Energy Resource which communicate control commands (e.g., Functional Schedules, Monitor Parameters). 

In [Massimiliano Masi, Giovanni Paolo Sellitto, Helder Aranha, Tanja Pavleska: Securing critical infrastructures with a cybersecurity digital twin. Softw. Syst. Model. 22(2): 689-707 (2023)](https://link.springer.com/article/10.1007/s10270-022-01075-0) we introduced a methodology to create a Digital Twin for Cybersecurity to facilitate the reasonings about the Cybersecurity posture of a generic Industrial Control System (ICS). The methodology is based on the following steps: 
* **Describe the ICS in Enterprise Architecture frameworks**: put all the processes, information, technologies, business objectives, and field considerations in a architectural framework such as [RAMI 4.0](https://ec.europa.eu/futurium/en/system/files/ged/a2-schweichhart-reference_architectural_model_industrie_4.0_rami_4.0.pdf) or SGAM.
* **Create a Cybersecurity Architectural View**: once the ICS is described and positioned in the layers of the EA framework, an architectural view spanning al the layers is created (the viewpoint is all the assets which Cybersecurity potential). This implement the concept that _Cybersecurity is a cross cutting concern_: cybersecurity is not something that should be considered at a technological level, but it shall be considered in all aspects of the software chain, from business objectives up to physical security considerations.
* **Create the Digital Twin of the assets of the CS View**: once the assets are added to the view, those assets are mapped to compoenents of the DT model. We use for that [coreLang](https://github.com/mal-lang/coreLang), a Domain Specific Language of the [Meta Attack Language (MAL)](https://www.mal-lang.org). Examples are: a DER unit becomes an "hardware device", where the firmware becomes a coreLang's "Application Component"
* **Start Reasoning**: Once the model is created, the reasoning starts by defining simulation scenarios from the business objectives: is my business objective correctly implemented by the architecture if Cyberattack occurs at various architectural layers?

Reasoning is performed using MAL simulations. 

# Running the examples

The model is created using [MAL GUI](https://github.com/mal-lang/mal-gui), and it is named `model.json`. Opening with the GUI will show the model. Then the `scenario.yml` depicts a very simple reasoning over the DER Use case
