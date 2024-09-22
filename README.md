# Background
**ACME Inc.** is a fictional company that develops a new SaaS B2C product. To refine its marketing strategy before the global launch the company decided to start with a soft launch: it would employ only three marketing channels to drive traffic to a simple landing page, which serves as an entry point to a sign-up process and ends with a service subscription purchase.

Below is a representation of the traffic journey and data sources (marketing channels, website analytics, CRM).

![BalsamiqWireframes_JF2vnM0pY5](https://github.com/user-attachments/assets/f94853bc-38fd-4998-b7b5-c19883e63d06)


# Deliverables
The deliverable of this project is a self-service solution in the form of a **Looker Studio dashboard** that would help the company's marketing team to analyze sales funnel efficiency and compare traffic sources' performance. 

![chrome_IfuDI8p5xv](https://github.com/user-attachments/assets/badf97e5-9228-4227-a38b-27f4faa858a4)

The dashboard's data source is a simplified **data warehouse** that consists of two layers: the core layer and the data mart layer, with Google Sheets as a storage backbone.

![BalsamiqWireframes_VrldezXpYy](https://github.com/user-attachments/assets/e31128f9-ec1e-4512-a4ab-4e50a93b383a)

Data processing handled by a **Python script** hosted on Google Colab.

### Links:
- Looker Studio dashboard: https://lookerstudio.google.com/reporting/a191e1ac-46bc-40d5-a956-6c6503c99c15
- Google Sheets DWH: https://docs.google.com/spreadsheets/d/170OPPnXPFcXoafin3eyAGN8v4Ht2x9MAKFWzwbbrbe4/edit?usp=sharing
- Google Colab Python script: https://colab.research.google.com/drive/1koQii_g2oa1dqF69pl-DIFCtci_8-Yq_?usp=sharing

# Recommendations
Underlying core layer data was intentionally generated to show the patterns below.

### Funnel:
- There was a 67% drop on the 23rd of August followed by a 48% rise on the 25th of August (compared to average values) in Conversion Rate which was mirrored by Cart Abandonment Rate on the same days. Campaigns that were active in those days might need **further research on the origin of such significant and synchronized movements of a needle**.
- There is a major 29% drop between the *Signup - Step 2* and *Signup - Step 3* events of the funnel followed by similar drops in later stages. While the funnel might have opportunities to streamline the process, marketing channels' **messages used in campaigns also might need to manage users' expectations more carefully**.

### Marketing:
- Comparing experimental *Influencers* channel with more traditional *Google Ads* and *Facebook Ads* **it stands out that *Influencers* looks promising**: it gives traffic with much better CR (x3-x4 times better) with comparable CAC.
- Between *Google Ads* and *Facebook Ads*, ***Facebook Ads* needs additional attention** since it performs worse on every metric, with CAC being the worst among all channels (x1.5-x3 times worse).

# Assumptions:
 - user journey begins and ends on the same day
 - one visitor makes only one purchase
 - no returning visitors, they either make a purchase or drop off somewhere along the funnel and never come back
 - funnel events are unique for a visitor, e.g. no two 'sigup_1' events
 - channel metrics are channel-level, no detalization
 - all outbound clicks from marketing channels are landed and registered as new visitors on a landing page
