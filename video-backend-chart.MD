helm create video-backend-chart


rm -rf video-backend-chart/templates/*



helm install telco-video-backend ./video-backend-chart --namespace realtime services
