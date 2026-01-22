# Insights Copilot - Comprehensive FAQ Documentation

**Last Updated:** January 19, 2026

**Version:** 2.0

**Maintained By:** Insights Copilot Product Team

**Review Cycle:** Every 3 weeks

# Overview
This FAQ provides comprehensive information about Insights Copilot, AB InBev's AI-powered decision thought partner. Whether you're a new user or looking to maximize your Insights Copilot experience, this guide covers everything from basic setup to advanced features.

---

# Getting Started

## What is Insights Copilot?
**Insights Copilot is AB InBev's proprietary AI-powered decision thought partner** that helps managers and executives derive insights from their own business data using natural language questions and brainstorm iteratively or deep dive into concerns according to their existing workflow to take faster data-driven decisions.

## Who can use Insights Copilot?
**All AB InBev employees can access Insights Copilot through SSO login**, but access to specific use cases depends on role and permissions. Only approved users from departments like Marketing, Supply Chain, and Procurement can access relevant use cases configured for their business domain.

**Primary User Personas:**
- **Managers** seeking data-driven insights for operational decisions
- **Executives** requiring strategic analysis and reporting
- **Business analysts** looking to accelerate their analytical workflows

**Secondary User Persona:**
- **Use Case Developers** customizing each use case to include business domain specific prompts and workflows to match user expectations

## How do I get started with Insights Copilot?
**New users follow this onboarding process:**
1. **Contact your use case admin** for initial demo and training
2. **Log in via SSO** using your AB InBev credentials
3. **Complete the quick onboarding guide** that appears on first login
4. **Learn best practices** for framing effective queries
5. **Start with simple questions** in your authorized use cases

## What should I expect during my first session?
**Your first Insights Copilot experience includes:**
- **Interactive onboarding guide** explaining Insights Copilot capabilities and limitations
- **Do's and don'ts** for effective query formulation
- **Sample questions** relevant to your authorized use cases
- **Tips for interpreting results** and follow-up queries

---

# Access and Permissions

## How do I access Insights Copilot?
**Insights Copilot is available as a web application** accessible through your browser using AB InBev SSO credentials. Simply navigate to the Insights Copilot portal and log in with your corporate credentials.

## What are the system requirements?
**Insights Copilot works on modern web browsers:**
- **Supported browsers:** Chrome, Edge, and Safari (latest versions recommended)
- **Internet connection:** Stable broadband connection for optimal performance (cannot be used offline at the moment)
- **Device compatibility:** Desktop and laptop computers (mobile browsers are not fully supported yet)
- **No additional software** installation required

## Which use cases can I access?
**Your access depends on your role and permissions.** Insights Copilot supports various business domains including Marketing, Supply Chain, Procurement, Logistics, Legal, and Strategy & Insights. Contact your use case admin or the Insights Copilot Product team to learn which use cases are available to you based on your role.

## How do I request access to additional use cases?
**To expand your access:**
1. **Contact your use case admin** for your current domain
2. **Reach out to the Insights Copilot Product team** via email to [ICProductteam@ab-inbev.com](mailto:ICProductteam@ab-inbev.com)
3. **Provide business justification** for the additional access needed
4. **Wait for approval** based on data permissions and business needs. You will be notified once access is granted.

---

# Using Insights Copilot

## What types of questions can I ask?
**Insights Copilot can answer questions within your authorized use cases.** The system is designed to handle natural language queries about your business data, enabling you to:
- Analyze trends and patterns in your data
- Compare metrics across different dimensions
- Retrieve specific data points and KPIs
- Explore relationships between different business variables

The specific types of questions you can ask depend on the data and use cases you have access to. Refer to your use case-specific documentation for detailed examples.

## How should I frame my queries for best results?
**Follow these best practices:**

**Do:**
- Be specific about time periods: "last quarter," "past 6 months," "2024 YTD"
- Specify relevant dimensions: brands, markets, categories, regions
- Use clear business metrics relevant to your domain
- Ask one question at a time for clearer results
- Provide context when asking follow-up questions

**Don't:**
- Use very complex queries with multiple intents
- Ask ambiguous questions without context
- Expect results outside your authorized use cases
- Request very large datasets that may impact performance

## What should I do if Insights Copilot doesn't understand my question?
**Try these approaches:**
1. **Rephrase your question** using simpler, more specific language
2. **Break complex queries** into smaller, focused questions
3. **Check if your question** falls within your authorized use cases
4. **Review the Know Your Data** feature to understand available data
5. **Escalate to your use case admin** if issues persist

## How long should I expect to wait for responses?
**Typical response times:**
- **Simple queries:** 10-30 seconds
- **Complex analysis:** 30 seconds to 1 minute
- **Smartflows:** May vary based on workflow complexity

---

# Features in Insights Copilot

## Chat
The core of Insights Copilot is its chat-based interface, enabling users to ask business questions in natural language and receive instant, data-driven responses. Insights Copilot can interpret follow-ups based on prior exchanges, making iterative exploration easy and natural. Response formats include summaries, tables, and charts (where supported), and users can clarify or refine questions seamlessly.

## Response Actions
**Insights Copilot provides several actions to enhance your analytical workflow:**

- **Feedback**: Instantly provide thumbs up/down and add comments for every response, feeding into product improvement and training
- **Share**: Share insights or chat segments with colleagues via secure links or export, supporting collaboration and knowledge transfer
- **Copy**: Copy results, tables, or summaries to clipboard for easy use in reports or presentations
- **Sources**: Inspect documents and external sources supporting a given answer for trust and compliance
- **Tables & Charts (WIP)**: Insights Copilot is piloting advanced data visualization directly within chat, allowing users to render and interact with tables (sort, filter, paginated) and charts (zoom, pan, download) as part of their analytical workflow

## Smartflows
Smartflows are guided analytical workflows designed to produce precise, business-ready reports with structured workflows. Questions are presented to the user as a fill in the blanks format with dropdowns from datasets for each blank, making it easy for any user to arrive at business deep-dives, even without deep technical knowledge. Smartflows also enforce high reproducibility and support best-practice reporting formats.

## Chat History
Everything you discuss with Insights Copilot is automatically stored in your chat history, allowing you to revisit, review, and build upon previous conversations. Chats are organized by date and use case context. This enables quick retrieval of past insights, supports regulatory and audit requirements, and helps new users learn from prior successful queries.

## Know Your Data
The "Know Your Data" feature gives users transparency into the underlying datasets powering Insights Copilot's responses. At any time, you can inspect the source, freshness, and lineage of data used in your analysis. This builds trust in Insights Copilot outputs and supports data governance objectives by providing context, definitions, and direct access to data dictionaries or relevant business glossaries.

## Use Case Switch
With a single click, users can switch between different configured use cases using the use case switch dropdown present at the top of the interface. The conversation context and analysis options automatically adjust to the selected use case. This flexibility helps users access relevant data, templates, and workflows without additional logins or navigation complexity, ensuring security and minimizing manual configuration errors.

## User Settings
The user settings panel allows for preferences and customization. Users can manage their display language (English, Spanish, Portuguese), change theme (light/dark) and delete their conversation history. Soon, it will also support response personalization and memory, helping users tailor Insights Copilot to their work style or business priorities.

---

# Data and Security

## What data sources does Insights Copilot access?
**Insights Copilot connects to:**
- **Databricks** for storing use case specific business data (direct/cleaned copy from BrewDat, AB InBev's internal data management system)
- **Domain-specific documents** relevant to each use case
- **Real-time and historical data** depending on source capabilities and use case configuration

## How current is the data Insights Copilot uses?
**Data freshness varies by source and use case:**
- **Most sources:** Updated daily, monthly, or quarterly as maintained by the data owners
- **Data timestamps** are shown when available in Sources and Know Your Data sections to provide transparency
- **Some data** may have inherent delays based on extraction and processing schedules from BrewDat or other systems

Always check the Know Your Data feature for specific information about data freshness for your use case.

## How does Insights Copilot protect my data and privacy?
**Insights Copilot follows AB InBev's strict security standards:**
- **SSO login** using Azure Cloud infrastructure ensures secure authentication
- **Role-based access control** ensures you only access authorized use cases and fetch associated data
- **Encryption** protects data in transit and at rest
- **Data retention policies** align with AB InBev's corporate guidelines
- **No data sharing** outside authorized users
- You can go through [Terms of Use](https://insights-copilot.ab-inbev.com/terms-of-use) and [Privacy Policy](https://insights-copilot.ab-inbev.com/privacy-policy) documents for more details

## Are there usage limits?
**Currently, no specific usage limits exist**, but the product will soon transition to a chargeback model where each business domain will be billed for usage. Usage limits may be established in the future as the platform scales.

---

# Technology Stack

## What technology powers Insights Copilot?
**Insights Copilot is built on a robust technology foundation:**

**Core AI Engine:**
- Langchain-based ReAct agent with Azure OpenAI GPT-4.1 model

**Backend Services:**
- Asynchronous REST-based services built on FastAPI framework
- Python-based response parser with Azure Functions

**Frontend:**
- React web app for conversation interface

**Data Infrastructure:**
- Databricks for storing use case data
- Postgres for storing app and user data
- Redis for caching
- Redis vector database for storing use case embeddings

**Storage & Infrastructure:**
- Azure blob storage for use case related documents
- Publicly hosted with SSO login using Azure Cloud infrastructure

---

# Troubleshooting

## What are common issues and solutions?

**"No data found" responses:**
- **Check your permissions** for the requested data
- **Verify the time period** you're asking about
- **Confirm data availability** using the Know Your Data feature
- **Try alternative time periods** or broader queries

**Unclear or irrelevant responses:**
- **Rephrase your question** more specifically
- **Provide more context** about what you're trying to analyze
- **Check if your query** matches available use cases
- **Break complex questions** into simpler parts

**Slow response times:**
- **Check your internet connection** stability
- **Try during off-peak hours** if possible
- **Simplify your query** to reduce processing time
- **Contact support** if issues persist

**Browser or technical issues:**
- **Clear your browser cache** and cookies
- **Try a different browser** from the supported list
- **Disable browser extensions** that might interfere
- **Check for corporate firewall** restrictions

## When should I escalate issues?
**Contact support when:**
- Insights Copilot consistently provides incorrect information
- You encounter technical errors or system failures 
- You have questions about data accuracy or sources
- You experience persistent performance issues like lag or timeouts

## How do I escalate problems?
**Escalation paths:**
1. **Response feedback:** Thumbs down on responses with detailed comments
2. **Product feedback:** Use the "Submit Feedback" option in the Help menu
2. **Use case admins:** Reach out to your primary contact for usecase-specific issues using "Contact Admin" option in the Help menu
3. **Insights Copilot Product team:** For technical issues and feature requests via email to [ICProductteam@ab-inbev.com](mailto:ICProductteam@ab-inbev.com)

---

# Providing Feedback

## How can I help improve Insights Copilot?
**Your feedback is valuable:**
- **Use thumbs up/down** on each Insights Copilot response to rate helpfulness
- **Provide detailed comments** about what worked or didn't work in your feedback
- **Share specific examples** of queries that need improvement
- **Suggest new features** or use cases you'd find valuable in your work
- **Report data accuracy issues** you discover for specific responses

## What feedback is most helpful?
**Prioritize feedback on:**
- **Accuracy of responses** and data quality
- **Relevance of insights** to your business questions
- **User experience issues** that slow down your work or create confusion
- **Missing capabilities** you need for your role
- **Ideas for new use cases** that would add value

---

# Current Limitations

## What can't Insights Copilot do today?
**Known limitations include:**

**Analytical Capabilities:**
- **No predictive analytics:** Insights Copilot cannot forecast future trends or outcomes
- **No prescriptive analytics:** Insights Copilot cannot recommend specific actions
- **Limited to descriptive analytics:** Insights Copilot analyzes what happened, not what will happen

**Query Complexity:**
- **Single intent queries work best:** Complex multi-part questions may confuse Insights Copilot
- **Limited ambiguity handling:** Vague questions may produce unclear results
- **No cross-use case analysis:** Insights Copilot cannot combine data across different use cases

**Technical Constraints:**
- **Large dataset limitations:** Very large queries may time out or perform slowly
- **Language support:** Only English, Spanish, and Portuguese are supported
- **Data source dependency:** Insights Copilot is limited to connected data sources
- **Analysis Template dependency:** Advanced analysis requires pre-configured templates

**Platform Limitations:**
- **Web-only access:** No mobile app or offline capabilities
- **No integrations:** Cannot currently embed in other AB InBev tools
- **Limited collaboration features:** Basic sharing capabilities only

## How do these limitations affect my usage?
**Plan accordingly:**
- **Ask focused questions** rather than broad, complex queries
- **Use separate queries** for different aspects of analysis
- **Verify critical insights** through additional sources when needed
- **Understand data boundaries** for your specific use cases
- **Consider manual analysis** for predictive or prescriptive needs

---

# Current Metrics

## How is Insights Copilot performing?
**Key performance indicators (as of 2025-2026):**
- **Activated users:** 5K (2025) → Target 10K+ (2026)
- **Monthly Active Users (MAU):** Tracked and targeted for growth
- **NPS:** Currently tracked

These metrics help the product team understand adoption and user satisfaction, guiding continuous improvement efforts.

---

# What's Coming Soon

## Near-term Enhancements (Next 3-6 months)
**Cognition:**
- **Memory features** to retain context across sessions
- **Improved natural language understanding** for complex queries
- **Enhanced response personalization** based on user preferences

**Enhanced User Experience:**
- **In-app feedback forms** for more detailed response evaluation
- **Improved query suggestions** based on your conversation history
- **Better visualization and export options** for presenting insights
- **Advanced table and chart interactions** with full rollout

**Platform Improvements:**
- **Mobile responsiveness** improvements for better mobile browser experience
- **Integration exploration** with other AB InBev tools
- **Enhanced collaboration features** for team-based analysis

---

# Competitive Landscape

## How does Insights Copilot compare to alternatives?
**Insights Copilot's differentiation comes from:**
- **Direct access to AB InBev's internal data** with proper credentials and security
- **Built in-house** for complete flexibility and customization
- **Domain-specific optimization** for AB InBev's business needs
- **Not bounded by third-party product architecture** limitations

**Direct Competitors:**
- Databricks Genie
- Max.AI by AnswerRocket
- Microsoft Copilot

**Indirect Competitors:**
- Power BI

**Internal Tools:**
- **Stellar**: For asking queries on IT documents and employee policies
- **GPTAP**: A ChatGPT wrapper routing employee queries to ChatGPT API with encryption

These internal tools address generic enterprise search needs for all employees on data public to enterprise, however Insights Copilot caters to a targeted customer segment with secure business datasets.

---

# Best Practices

## Maximizing Your Insights Copilot Experience

**Query Formulation:**
- Start with simple questions to understand Insights Copilot's capabilities in your domain
- Use specific business terms and metrics that Insights Copilot recognizes
- Include time periods, geographic regions, and relevant dimensions
- Ask follow-up questions to drill deeper into interesting insights

**Data Interpretation:**
- Always consider the data source and freshness when interpreting results
- Use the View Sources and Know Your Data features to verify information
- Cross-check critical insights with other sources when making important decisions
- Understand the limitations of descriptive analytics for future planning
- Use Insights Copilot insights as starting points for deeper investigation

**Workflow Integration:**
- Use Insights Copilot for routine reporting and basic analysis tasks
- Leverage Smartflows for standardized reporting needs
- Combine insights from Insights Copilot with your domain expertise for comprehensive analysis
- Share relevant insights with team members to multiply value
- Save and revisit previous conversations through Chat History

**Continuous Learning:**
- Experiment with different query phrasings to understand Insights Copilot's capabilities
- Provide feedback to help improve Insights Copilot's performance over time
- Stay updated on new features and use cases as they become available
- Participate in training sessions and user communities
- Review your use case-specific documentation for domain-relevant examples

---

# Getting Help

## Support Resources

**Primary Contacts:**
- **Use Case Admin:** Your domain-specific expert for training and advanced questions
- **Insights Copilot Product Team:** For technical issues, feature requests, and system problems via email to [ICProductteam@ab-inbev.com](mailto:ICProductteam@ab-inbev.com)
- **Corporate IT Support:** For SSO, browser, or connectivity issues

**Self-Service Resources:**
- **This FAQ:** Comprehensive guide to Insights Copilot capabilities and usage
- **Onboarding prompt guide:** Tips for effective Insights Copilot usage
- **Use case-specific documentation:** Detailed information about your authorized domains

**Community Support:**
- **User communities:** Connect with other Insights Copilot users in your domain via dedicated Teams channels
- **Knowledge sharing sessions:** Regular updates on new features and capabilities
- **Feedback channels:** Contribute to Insights Copilot improvement through structured feedback

## Contact Information

**For immediate technical issues:**
- Use internal corporate support channels
- Document specific error messages and steps to reproduce

**For feature requests and feedback:**
- Contact the Insights Copilot Product team via email to [ICProductteam@ab-inbev.com](mailto:ICProductteam@ab-inbev.com)
- Provide detailed use cases and business justification

**For access and permissions:**
- Start with your use case admin
- Escalate to the product team if needed with business justification

---

# Conclusion

Insights Copilot is designed to accelerate data-driven decision-making across AB InBev. As AB InBev's proprietary AI-powered decision thought partner, it provides managers and executives with the ability to derive insights from their own business data using natural language, enabling faster and more informed decisions.

While Insights Copilot has current limitations, ongoing development continues to expand its capabilities and improve user experience. By following best practices and providing feedback, you help shape Insights Copilot's evolution to better serve our business needs.

Remember that Insights Copilot is most effective when used as part of your analytical toolkit, combining AI-powered insights with your domain expertise and business judgment. As we continue to enhance Insights Copilot's capabilities, your engagement and feedback are essential for ensuring it meets our evolving business needs.

**Questions not covered in this FAQ?** Contact your use case admin or the Insights Copilot Product team for assistance.