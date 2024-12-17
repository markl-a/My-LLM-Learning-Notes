# MachineLearningNote

1_ML_and_Data_Analysis/：
包含機器學習基礎、資料分析、傳統ML演算法、EDA、特徵工程、Kaggle案例、分散式運算、大數據處理與ETL流程整合。

2_DL/：
集中深度學習主題，區分「電腦視覺」與「NLP & 語音」兩大領域。包含理論、實作範例，以及經典與現代研究論文的摘要。

3_MLOps_and_Deployment/：
包含MLOps的概念、CI/CD、MLflow、Kubeflow、Airflow、模型漂移監測、容器化與多雲端部署操作範例。

4_Cloud_and_Infrastructure_Integration/：
處理雲端整合議題，包含Serverless、IAM、安全性、API Gateway、CDN、負載平衡等雲端基礎建設與ML系統整合方法。
```
ml-dl-notes/
├─ README.md                       # 專案總覽與導讀
├─ 1_ML_and_Data_Analysis/
│  ├─ README.md
│  ├─ fundamentals/
│  │  ├─ mathematics/
│  │  │  ├─ linear_algebra_basics.md
│  │  │  ├─ probability_statistics.md
│  │  │  └─ calculus_and_optimization.md
│  │  ├─ python_data_analysis/
│  │  │  ├─ numpy_pandas_basics.ipynb
│  │  │  ├─ data_visualization_matplotlib.ipynb
│  │  │  ├─ seaborn_intro.ipynb
│  │  │  └─ eda_examples.ipynb
│  │  └─ data_preprocessing/
│  │     ├─ missing_values_handling.ipynb
│  │     ├─ feature_scaling_normalization.ipynb
│  │     ├─ feature_encoding_categorical_data.ipynb
│  │     └─ dimensionality_reduction_pca.ipynb
│  ├─ theory/
│  │  ├─ ml_concepts_overview.md
│  │  ├─ bias_variance_tradeoff.md
│  │  ├─ regularization_ridge_lasso.md
│  │  ├─ underfitting_overfitting_explained.md
│  │  ├─ statistical_learning_theory.md
│  │  ├─ vc_dimension.md
│  │  └─ pac_learning_summary.md
│  ├─ algorithms_and_models/
│  │  ├─ linear_models/
│  │  │  ├─ linear_regression_theory.md
│  │  │  ├─ linear_regression_example.ipynb
│  │  │  ├─ logistic_regression_theory.md
│  │  │  └─ logistic_regression_example.ipynb
│  │  ├─ tree_based_models/
│  │  │  ├─ decision_tree_theory.md
│  │  │  ├─ decision_tree_example.ipynb
│  │  │  ├─ random_forest_theory.md
│  │  │  ├─ random_forest_example.ipynb
│  │  │  └─ gradient_boosting_methods.md
│  │  ├─ svm/
│  │  │  ├─ svm_theory.md
│  │  │  ├─ svm_example.ipynb
│  │  │  └─ kernel_methods_explained.md
│  │  ├─ knn_nb/
│  │  │  ├─ knn_theory.md
│  │  │  ├─ knn_example.ipynb
│  │  │  ├─ naive_bayes_theory.md
│  │  │  └─ naive_bayes_example.ipynb
│  │  ├─ clustering/
│  │  │  ├─ kmeans_theory.md
│  │  │  ├─ kmeans_example.ipynb
│  │  │  ├─ hierarchical_clustering.md
│  │  │  └─ dbscan_example.ipynb
│  │  ├─ evaluation_metrics.md
│  │  └─ cross_validation_techniques.md
│  ├─ applications/
│  │  ├─ eda_workflow.md
│  │  ├─ feature_engineering_tips.md
│  │  ├─ hyperparameter_tuning_examples.ipynb
│  │  ├─ kaggle_competitions/
│  │  │  ├─ intro_to_kaggle.md
│  │  │  ├─ titanic_survival_example.ipynb
│  │  │  ├─ house_price_prediction.ipynb
│  │  │  └─ model_submission_tips.md
│  │  └─ model_deployment_simple_example.ipynb
│  ├─ data_analysis_and_processing/  
│  │  ├─ data_cleaning_etl/
│  │  │  ├─ etl_concepts_overview.md
│  │  │  ├─ data_cleaning_pipeline_example.ipynb
│  │  │  ├─ scheduling_etl_airflow.md
│  │  │  └─ data_quality_checks.md
│  │  ├─ structured_unstructured_data/
│  │  │  ├─ sql_data_analysis.ipynb
│  │  │  ├─ nosql_basics.md
│  │  │  └─ text_image_json_parsing_examples.ipynb
│  │  ├─ excel_python_sql/
│  │  │  ├─ excel_analysis_tips.md
│  │  │  ├─ python_sql_integration.ipynb
│  │  │  └─ reporting_automation_examples.ipynb
│  │  └─ distributed_processing/
│  │     ├─ hadoop_intro.md
│  │     ├─ spark_pyspark_basics.ipynb
│  │     ├─ optimizing_big_data_pipelines.md
│  │     └─ integrating_big_data_with_mlops.md
│  └─ papers/
│     ├─ classic_papers_summary.md
│     ├─ random_forest_breiman_paper.md
│     ├─ svm_paper_notes.md
│     └─ domain_research_links.md
│
└─ 2_DL/
   ├─ README.md
   ├─ computer_vision/               # 原1.1.2內容
   │  ├─ theory/
   │  │  ├─ neural_network_basics.md
   │  │  ├─ convolutional_neural_networks.md
   │  │  ├─ transfer_learning.md
   │  │  └─ object_detection_segmentation_intro.md
   │  ├─ frameworks/
   │  │  ├─ tensorflow_pytorch_basics.ipynb
   │  │  └─ keras_cnn_example.ipynb
   │  ├─ examples/
   │  │  ├─ image_classification_cifar10.ipynb
   │  │  ├─ image_augmentation_techniques.ipynb
   │  │  └─ fine_tuning_resnet.ipynb
   │  └─ papers/
   │     ├─ alexnet_paper_summary.md
   │     ├─ vgg_resnet_comparison.md
   │     └─ modern_vision_transformers_summary.md
   ├─ nlp_and_speech/                # 原1.1.3內容
   │  ├─ theory/
   │  │  ├─ nlp_basics_tokenization.md
   │  │  ├─ rnn_lstm_gru_theory.md
   │  │  ├─ transformer_bert_gpt_overview.md
   │  │  └─ speech_recognition_theory.md
   │  ├─ examples/
   │  │  ├─ sentiment_analysis.ipynb
   │  │  ├─ text_classification_tf_idf.ipynb
   │  │  ├─ word_embeddings_word2vec_glove.md
   │  │  ├─ huggingface_transformers_example.ipynb
   │  │  └─ simple_speech_recognition_example.ipynb
   │  └─ papers/
   │     ├─ word2vec_paper_summary.md
   │     ├─ bert_paper_notes.md
   │     └─ seq2seq_speech_papers_summary.md
   └─ frameworks_resources.md        # 可加入對各DL框架資源的整理(選填)


3_MLOps_and_Deployment/
├─ README.md
├─ mlops_concepts_overview.md
├─ model_lifecycle_management.md
├─ ci_cd_pipelines/
│  ├─ github_actions_example.md
│  ├─ jenkins_integration_tutorial.md
│  └─ azure_devops_pipeline.md
├─ mlflow/
│  ├─ mlflow_basics.ipynb
│  ├─ model_versioning.md
│  └─ model_serving_examples.md
├─ kubeflow/
│  ├─ kubeflow_pipeline_intro.md
│  ├─ pipeline_example.ipynb
│  └─ model_monitoring_kubeflow.md
├─ airflow/
│  ├─ airflow_for_etl.md
│  ├─ dag_example.py
│  └─ ml_pipeline_integration.md
├─ model_drift_and_monitoring/
│  ├─ concept_drift_explained.md
│  ├─ drift_detection_tools.md
│  └─ monitoring_dashboard_example.md
└─ containerization_and_deployment/
   ├─ docker_basics.md
   ├─ kubernetes_intro.md
   ├─ aws_sagemaker_deployment.md
   ├─ azure_ml_service_deployment.md
   └─ gcp_ai_platform_deployment.md

4_Cloud_and_Infrastructure_Integration/
├─ README.md
├─ serverless_architecture/
│  ├─ aws_lambda_intro.md
│  ├─ azure_functions_example.md
│  └─ gcp_cloud_functions_guide.md
├─ iam_and_security/
│  ├─ aws_iam_basics.md
│  ├─ azure_ad_roles.md
│  └─ securing_ml_endpoints.md
├─ api_gateway/
│  ├─ api_gateway_concepts.md
│  ├─ rest_api_example_flask.md
│  └─ authentication_authorization.md
├─ cdn_and_load_balancing/
│  ├─ cdn_overview.md
│  ├─ aws_cloudfront_example.md
│  └─ load_balancer_patterns.md
└─ integration_patterns/
   ├─ ml_service_scaling_strategies.md
   └─ monitoring_logging_cloud_services.md
```
