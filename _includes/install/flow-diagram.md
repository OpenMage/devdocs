![How Magento installation works]({{ site.baseurl }}/common/images/installation/installation-flow.png)

The diagram shows the following:

1.	Set up your server environment.

	Install the prerequisite software, including PHP, Apache, and MySQL. Consult the [system requirements]({{ site.gdeurl }}/system-requirements.html) for specific information:

2.	Get the Magento LTS software.

	* Download the latest archive and extract it, clone the repo, or add a composer dependency to your existing project like so:
```json
"openmage/magento-lts": "1.9.4.x"
```

	* Use one of the two compose install

	* If you want to contribute to the {{site.data.var.om}} codebase, customize the Magento application or fix and test your own code, [fork]({{ page.baseurl }}/install-gde/prereq/dev_install.html) the Magento-LTS GitHub repository. (This method requires familiarity with both GitHub.) Follow [Contributor]


3.	Install the Magento software using either the Web Setup Wizard or command line.

	For simplicity, only the Web Setup Wizard is shown in the diagram.

	At each step, the Web Setup Wizard validates the information you entered. As shown in the preceding diagram, if validation fails, you must manually fix the issues before you proceed.

	If the step fails because prerequisite software isn't set up correctly, review our [Prerequisites](/install-gde/prereq/prereq-overview.html).

4.	Verify the installation by viewing your storefront and the Magento Admin.
