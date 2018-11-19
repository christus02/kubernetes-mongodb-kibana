# Kubernetes Demo Application : Customer Portal

This is the demo application for kubernetes comprising of mongoDB, elastic search, kibana and frontend application.
The landing page has a customer portal form, which upon successfull completion, the data would be stored into mongoDB.
The data in the mongoDB would be pushed to elastic search on every write using a python parser.
This data in elastic search can now be visualized in Kibana.


