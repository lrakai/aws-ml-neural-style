# aws-ml-neural-style
Use an MXNet neural network and a p2.xlarge (GPU) instance to transfer artistic style to photos

![Lab objective](https://user-images.githubusercontent.com/3911650/33281128-6b01d19e-d361-11e7-840d-06fc69ce9565.png)

## Getting Started
Deploy the CloudFormation stack in the template in `infrastructure/`. The template creates a user with the following credentials and minimal required permisisons to complete the Lab:
- Username: _student_
- Password: _password_

## Instructions
- Connect to the instance using the SSH username: _ubuntu_. 
- Change into the `/home/ubuntu/src/mxnet/example/neural-sytle` directory
- Run the [GPU monitoring script developed by AWS](https://s3.amazonaws.com/aws-bigdata-blog/artifacts/GPUMonitoring/gpumon.py): `python gpumon.py`
- Perform a neural style transfer by executing the following command:
```bash
python nstyle.py --content-image input/IMG_4343.jpg \
                 --style-image input/starry_night.jpg \
                 --gpu 0 \
                 --output_dir output/ \
                 --save-epochs 20 \
                 --max-num-epochs 300
```

## Cleaning Up
Delete the CloudFormation stack to remove all the resources. No resources are created outside of those created by the template.