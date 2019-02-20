
    pipeline {
    
        //agent any 
        agent { label 'rhel' }
        
    	
        stages{

            stage('New Commit(s) Detected') {
                steps {
					sleep(4)
					sh "echo 'listing new changes....'"
				}
			}
		
            stage('Pull Code from SCM ') {
                steps {
                    script{
						sleep(4)
                        sh "echo 'Running Git pull from repository...'"
                    }
                    
                }
            }
			
            stage('Build and Unit Test') {
                steps {
                    script{
						sleep(2)
                        sh "echo 'Running Maven Build...'"
						sleep(2)
						sh "echo 'Running Junit Tests...'"
                    }
                    
                }
            }			
            stage('SonarQube Analysis') {
                steps {
                    script{
						sleep(2)
                        sh "echo 'Performing Sonar Quality and Coverage Scans...'"
						sleep(2)
						sh "echo 'Publishing scan results to Sonar Server...'"
                    }
                    
                }
            }			
            stage('Quality Gate') {
                steps {
                    script{
						sleep(4)
                        sh "echo 'Performing Quality Gate checks to proceed further...'"
                    }
                    
                }
            }			
            stage('Dockerize') {
                steps {
                    script{
						sleep(4)
                        sh "echo 'Dockerize the Artifact...'"
                    }
                    
                }
            }			
            stage('Security scan for Image') {
                steps {
                    script{
						sleep(4)
                        sh "echo 'Performing Security Scans on Docker Image...'"
                    }
                    
                }
            }
            stage('Push Image to Docker Registry') {
                steps {
                    script{
						sleep(4)
                        sh "echo 'Pushing the latest Docker image to Docker Registry...'"
                    }
                    
                }
            }
            stage('Deploy to QA') {
                steps {
                    script{
						sleep(4)
                        sh "echo 'Deploying the latest Docker image to QA Environment'"
                    }
                    
                }
            }
			stage('Automated Acceptance Tests') {
				parallel {
					stage('Mozilla') {
					
						stages{
							stage('Prepare Test Data'){
								steps {
									echo "Preparing Test Data..."
								}
							}
							stage('Perform Tests'){
								steps {
									echo "Performing Tests..."
								}
							}
						}
					}
					stage('IE') {
					
						stages{
							stage('Prepare Test Data'){
								steps {
									echo "Preparing Test Data..."
								}
							}
							stage('Perform Tests'){
								steps {
									echo "Performing Tests..."
								}
							}
						}
					}
					stage('Chrome') {
					
						stages{
							stage('Prepare Test Data'){
								steps {
									echo "Preparing Test Data..."
								}
							}
							stage('Perform Tests'){
								steps {
									echo "Performing Tests..."
								}
							}
						}
					}

				}
			}            
            stage('Manual Test Approval') {
                steps {
                    script{
						sleep(1)
                        sh "echo 'Approve to proceed if manual tests are passed'"
						
                    }
                    
                }
            }
            stage('Deploy on UAT') {
                steps {
                    script{
                        sh "echo 'Deploy latest image on UAT'"
						sleep(4)
                    }
                    
                }
            }
            stage('Automated User Acceptance tests') {
                steps {
                    script{
                        sh "echo 'Perform User Acceptance tests'"
						sleep(4)
                    }
                    
                }
            }
            stage('Deploy on Stage') {
                steps {
                    script{
                        sh "echo 'Deploy latest image on Stage'"
						sleep(4)
                    }
                    
                }
            }
            stage('Regression tests') {
                steps {
                    script{
                        sh "echo 'Perform Regression tests'"
						sleep(4)
                    }
                    
                }
            }
            stage('Release to Prod ?') {
                steps {
                    script{
                        sh "echo 'Ok to release to Prod ?'"
						sleep(4)
                    }
                    
                }
            }
            stage('Release') {
                steps {
                    script{
                        sh "echo 'Release to Production'"
						sleep(4)
                    }
                    
                }
            }
        }
    }
