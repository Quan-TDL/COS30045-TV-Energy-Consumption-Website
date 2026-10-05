# COS30045-Demonstration Week 4 - Data Story

## Audience and Interest

I designed this data story for **first-time TV buyers in Australia**. There are so many TV sizes and screen technologies on the market that it's hard to know where to start.

The story is built around two connected questions:

1. **How common is each size of TV?**
2. **How does screen type affect energy consumption?**

The first question shows which sizes are most available in Australia. The second looks at how energy consumption differs between LCD, LCD (LED) and OLED TVs across different screen sizes.

My main message is that **TV size has a strong relationship with energy consumption**, while screen technology becomes more useful when comparing TVs of a similar size. So a buyer should first decide on a suitable screen size, then compare the energy use of different technologies and individual models.

I used two charts to tell this story:

- **TV Screen Sizes** – a histogram showing the distribution of TV screen sizes.
- **Screen Type & Energy Use** – a grouped bar chart comparing average labelled energy consumption by screen technology and TV size.

---

# About the Data

## Data Source

The data comes from the **Energy Rating Data for household appliances – Labelled Products** dataset, published by the **Australian Government Department of Climate Change, Energy, the Environment and Water (DCCEEW)**.

It is available on Data.gov.au:

- [DCCEEW organisation page](https://data.gov.au/data/organization/dcceew)
- [Energy Rating Data for household appliances – Labelled Products](https://data.gov.au/data/dataset/energy-rating-for-household-appliances)

The dataset covers products that carry the Energy Rating Label, including televisions. I used only the television data for this project.

Suppliers provide the data when they register appliances for sale in Australia and New Zealand. The fields vary by product type and can include model information, where the product is sold, availability, star rating and other product-specific details.

DCCEEW was formed on 1 July 2022. The dataset is provided under the **Creative Commons Attribution 3.0 Australia** licence.

## Data Processing

I processed the original television dataset in KNIME before creating the visualisations. The main steps were:

1. I filtered the dataset to keep only televisions sold in Australia.
2. I then kept only televisions with an availability status of **Available**.
3. I focused on three variables:
   - screen size,
   - screen technology, and
   - labelled energy consumption (kWh/year).
4. Screen size was recorded in centimetres, so I converted it to inches using `screen size × 0.393701`.
5. I grouped TVs into three screen-size categories:
   - **Small:** below 43 inches
   - **Medium:** 43 to 65 inches
   - **Large:** above 65 inches
6. For the first visualisation, I used the screen-size data to show how frequently each size appears.
7. For the second visualisation, I used average labelled energy consumption to compare LCD, LCD (LED) and OLED TVs across the three size categories.

While cleaning the data, I also looked into repeated model numbers. Some of them had different screen sizes or energy values, so I didn't treat them as duplicates automatically. I did find a small number of exact duplicate records, but I kept them because they made up less than 1% of the cleaned dataset and were unlikely to change the overall trends.

After the Australia and availability filters, the working dataset had **4,508 records**.

## Privacy

This dataset is about registered appliance products, not individual consumers. My analysis only uses product information: screen size, screen technology, availability and labelled energy consumption.

The original Energy Rating registration system may collect personal and organisational information from suppliers for registration and regulatory purposes. I didn't need any of that information for my analysis, and no personal information about consumers was collected, analysed or shown in this project.

## Accuracy and Limitations

The dataset is useful for exploring televisions and their labelled energy consumption, but it has some limitations.

First, it only represents products registered by suppliers, so it isn't necessarily a complete picture of every TV Australians buy or use. It also covers both Australia and New Zealand, which is why I had to filter it down to Australia.

Second, the data has repeated model numbers and some unusual values. I investigated the repeated model numbers instead of removing them because some had different screen sizes or energy values. This means a row shouldn't automatically be read as one unique TV model.

Third, my analysis shows relationships between variables, but it doesn't prove that one factor directly causes a change in energy use. Screen technology shouldn't be treated as the only factor affecting energy consumption, because screen size and other product features also play a part.

Finally, I used averages to compare screen technologies, and averages can hide variation between individual models.

## Ethics

I tried to present the data accurately and avoid misleading conclusions. The visualisations are based on a published government dataset, and I've acknowledged the source so the audience can see where the information came from.

I was careful not to make unsupported claims, such as saying one screen technology is always more energy efficient than another. The results are patterns and comparisons within this dataset, not universal conclusions about all televisions.

I investigated potential data-quality issues rather than quietly removing records, and I avoided using or displaying any personal information.

---

# AI Declaration

I used generative AI as a support tool during this project. ChatGPT helped me with:

- planning and checking the data-cleaning workflow in KNIME;
- identifying possible data-quality issues, including repeated model numbers and unusual screen-size values;
- exploring possible trends and relationships in the dataset;
- identifying and refining the target audience for the data story;
- developing the two connected data questions;
- planning the visualisation story and deciding which charts would best communicate the findings;
- drafting and refining the written data story;
- helping with the HTML structure and CSS for the `datastory.html` webpage;
- helping with the README structure and wording.

I reviewed the final data processing decisions, visualisations, website and content, and I take responsibility for what I've submitted.


# COS30045-Exercise-0.2
Build Appliance Energy Consumption Website

## Generative AI Reflection

I used ChatGPT as a Generative AI tool throughout the development of this website.

I used Generative AI to assist with the overall website structure and to generate HTML, CSS and JavaScript code. This included creating the navigation bar, styling the website, implementing the FAQ accordion, organising the project folders, and providing guidance on connecting the different files.

Most of the initial code was generated with the assistance of ChatGPT. I then reviewed the generated code, added it to my project, tested it, and made adjustments when necessary to match the requirements of the assignment and my project structure.

Through using Generative AI, I learned how HTML is used to structure a webpage, how external CSS is used to control the appearance of multiple pages, and how JavaScript can provide interactive features such as the FAQ accordion. I also learned how relative file paths are used to connect HTML, CSS, JavaScript and image files.

One limitation I encountered was that generated code may depend on the correct file names, folder structure and HTML classes. Code generated by AI therefore still needs to be checked and tested to ensure that it works correctly in the actual project.