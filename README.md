# Are We There Yet? Alexa Market Comparison
Files used to organise and corectly map tracebaility data for Alexa skills between csv and json files during three different years 2019, 2020, 2021. This repo also contains example executions that show how to compare the datasets over the years.

# Outline
<ul>
  <li>CreateDatasets: ipynbs used to created the datasets and to map skills between years. Details can be found in CreateDatasets/process.txt file.</li>
  <li>datasets: folder containing the datasets created. The latest ones and these which should be used are those taht end with '*_ids.csv'. Since I cannot upload the datasets to github, this folder probably includes a zip files with the datasets in it.</li>
  <li>LoadDatasets.ipynb: Example ipynb file with some example executions as how to load and analyse the data provided in the datasets</li>
</ul>

# Dataset columns
<ul>
  <li>id_name_dev: str - formed by appending columns 'name'+'__'+'dev'. It is used to assign id and map skills between years.</li> 
  <li>id_aux: str (unused column) - auxiliar id formed by appending columns 'name'+'__'+'dev'+'__'+amazonid (amazon id was not available in early crawlings of the dataset. It's replaced by an empty string if amazonid was not found in the crawling. </li>
  <li>name: str - name of the skill.</li> 
  <li>dev: str - developer.</li>
  <li>cat: str - main category at the moment of the crawling</li>
  <li>subcat: str - subcategory at the moment of crawling</li>
  <li>market: str - 2char string indicating the market. e.g. 'US', 'UK', ...</li>
  <li>acc_linking: str - String indicating if the skill allowed account linking. </li>
  <li>cost: str - string that indicates whether the skill was free to enable or not.</li>
  <li>in_skill_purchase: str - String indicating whether the skill allowed in-skill purchases </li>
  
  <li>review_stars: str - String indicating how many stars has the skill as crawled (if found). </li>
  <li>skill_link: str - string indicating the information displayed for skill link as displayed in the moment of crawling.</li>
  <li>year: int - year that the entry was crawled.</li>
  <li>perm_requested_original: list<str> - Original list of permissions collected at the moment of crawling. Note that permissions changed over the years. All markets have this information </li>
  <li>perm_requested_norm: list<str> - Normalised list of original permissions collected at the moment of crawling, as presented in the latest paper.</li>
  <li>perm_found_norm: list<str> - Permissions found in the policy of the skill, as collected by SkillVet. Only skills from english markets (US, UK, IN, CA, AU) with a policy have this information filled.</li>
  <li>traceability: char - Traceability of the skill (B broken, P partial, C complete), assigned using SkillVet. Only skills from english markets (US, UK, IN, CA, AU) with a policy have this information filled.</li>
  <li>policy_url: str - Url to the skill's policy (if any).</li>
  <li>policy_text: str - Policy text, raw.</li> 
</ul>

# Combined Report
CombineReport is the combination of all reported skills with bad traceability. These are skills reported to Amazon and developers previously. Their traceability changes can be obtained when comparing the current traceabilities with these found when they were reported.

