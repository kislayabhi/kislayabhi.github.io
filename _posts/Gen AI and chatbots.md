## Notes from Gen AI and LLMs by David Baum

1. Traditional AI vs Generative AI
    - Traditional AI uses predictive models to
      - classify data
      - recognize pattern
      - and predict outcomes within a specific context or domain
         - such as analyzing medical images
     - Gen AI models generate:
       - entirely new outputs rather than
       - simply making predictions based on prior experience.
      
2. What does this mean?
   - This means there is an underlying shift from prediction to creation
   - Which ultimately opens up new realms of innovation.

3. What are my aims in reading through this book?
   - This provides an introductory overview of LLMs and gen AI applications,
   - Along with techniques for training, tuning, and deploying machine learning models
   - To get a technical foundation without getting into the weeds.
   - and to help bridge the gap between AI experts and their counterparts in other departments

4. Introducing LLMs and foundation models
   - Some context on the large language models that I know
   - Today's LLMs power many modern applications:
     - Content creation tools
     - Language translation apps
     - Customer service chatbots
     - Financial analysis sites
     - Scientific research repositories
     - Advanced internet search tools
 5. A key breakthrough came in 2017 when the Google Brain team introduced the transformer architecture.
     - This deep learning model replaced traditional recurrent and convolutional structures
     - with a new type of architecture that is particularly effective at understanding and contextualizing language
     - as well as generating text, images, audio, and computer code.
 6. GPUs have a large number of cores that can process multiple tasks simultaneously.
     - Transformers use GPUs to process multiple threads of information
     - Leading to faster training of AI models that effectively handle not just text but also images, audio, and video content.
     - This parallel processing capability is crucial for the computationally intensive calculations involved in ML, such as matrix operations.
 7. Gen AI applications that have been built on public data can't realize their full potential in the enterprise until they are coupled with enterprise data stores.
     - Most organizations store massive amounts of data, both on-premises and in the cloud.
     - Many of these businesses have data science practices that leverage structured data for traditional analytics, such as forecasting
     - To maximize the value of gen AI, these companies need to open up to the vast world of unstructured and semistructured data as well.
     - 80 to 90 percent of data is unstructured - locked away in text, audio, social media, and other sources.
 8. CAST A WIDE DATA NET
     - To maximize the potential of your genAI endeavors, cast a wide net to utilize three basic types of data sources:
       - First-party data is internal data produced via everyday business interactions.
       - Second-party data is produced by collaboration with trusted partners.
       - Third-party data can be acquired from external sources to enrich internal data sets.
  9. Today's LLMs have paved the way for an immense array of advanced applications centered around:
      - Content generation: Generating various types of media, including text, sound, and images.
      - Logical reasoning: They can unravel the underlying meaning in textual data. This helps in sentiment analysis and other complex reasoning tasks that involve extracting meaningful insights from text and providing a deeper understanding of human language.
      - Language Translation: LLMs can accurately convert text from one language to another, ensuring effective and reliable translation.
      - Text Retrieval, Content Summarization, and Search: LLMs are pre-trained on vast amounts of text data, allowing them to grasp the nuances of language and comprehend the meaning of the text. They can search through large databases or the internet in general to locate relevant information based on user-defined queries.
      - Code generation
  10. One thing to note is - the Gen AI models and the decisions made from those models are only as good as the data that supports them. The more data these models ingest and the more situations they encounter, the smarter and more comprehensive they become.


## Pre-trained models

There's a rapidly growing market for creating and customizing gen AI foundational models. This has given rise to a surge of LLMs that have been pre-trained on data sets with millions or even billions of records.

The challenge facing today's enterprise involves augmenting LLMs with this corporate data in a secure and governed manner. 

1. Start by unifying data in a comprehensive repository that multiple workgroups can access easily and securely. This allows for centralized data governance and democratizing access to gen AI initiatives across your organization while minimizing complexity and optimizing costs. I think a good data pipeline is essential in leveraging Gen AI solutions.
2. General purpose LLMs --> Contextually trained LLMs. A foundational model serves as the basis for developing specialized applications adapted to specific industries, business problems, and use cases. A foundational model can often be multimodal, meaning it handles both text and other media such as images. 
