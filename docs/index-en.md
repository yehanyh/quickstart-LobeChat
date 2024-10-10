<h1> Rapid deployment of the LobeChat computing nest </h1>

<blockquote>
    <p><strong> Disclaimer:</strong> This service is provided by a third party. We try our best to ensure its security,
        accuracy and reliability, but we cannot guarantee that it is completely free from failure, interruption, error
        or attack. Therefore, the company hereby declares that it makes no representations, warranties or commitments
        regarding the content, accuracy, completeness, reliability, suitability and timeliness of the Service and is not
        liable for any direct or indirect loss or damage arising from your use of the Service; for third-party websites,
        applications, products and services that you access through the Service, do not assume any responsibility for
        its content, accuracy, completeness, reliability, applicability and timeliness, and you shall bear the risks and
        responsibilities of the consequences of use; for any loss or damage arising from your use of this service,
        including but not limited to direct loss, indirect loss, loss of profits, loss of goodwill, loss of data or
        other economic losses, even if we have been advised in advance of the possibility of such loss or damage; we
        reserve the right to amend this statement from time to time, so please check this statement regularly before
        using the Service. If you have any questions or concerns about this Statement or the Service, please contact us.
    </p>
</blockquote>

<h2> Overview </h2>

<p>LobeChat is a modern open source ChatGPT/LLMs chat application and development framework <br/>
    It supports speech synthesis, multi-modal, and extensible (<a
            href="https://lobehub.com/zh/blog/openai-function-call">function call</a>) plug-in system. You can use
    LobeChat to have your own ChatGPT/Gemini/Claude/Ollama application for free with one click </p>

<h2> Prerequisites </h2>

<p><font style="color:white;"> To deploy a Dify Community Edition service instance, you need to access and
    create some Alibaba Cloud resources. Therefore, your account must contain permissions for the following
    resources. </font><font style="color:white;"> </font><strong><font style="color:white;">
    Description </font></strong><font style="color:rgb(51, 51>: 51);">: this permission is required only when your account is a RAM account. </font></p>

<table>
<thead>
<tr>
    <th><font style="color:white;"> Permission policy name </font></th>
    <th><font style="color:white;"> Remarks </font></th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td><font style="color:white;">AliyunECSFullAccess</font></td>
        <td><font style="color:white;"> Permissions to manage ECS </font></td>
    </tr>
    <tr>
        <td><font style="color:white;">AliyunVPCFullAccess</font></td>
        <td><font style="color:white;"> Permissions to manage a VPC </font></td>
    </tr>
    <tr>
        <td><font style="color:white;">AliyunROSFullAccess</font></td>
        <td><font style="color:white;"> Manage permissions for the Resource Orchestration Service
            (ROS) </font></td>
    </tr>
    <tr>
        <td><font style="color:white;">AliyunComputeNestUserFullAccess</font></td>
        <td><font style="color:white;"> Manage user-side permissions for the compute nest service
            (ComputeNest) </font></td>
    </tr>
    </tbody>
    </table>

<h2> Billing instructions </h2>

<p><font style="color:white;"> The cost of LobeChat community edition deployment in computing nest mainly
    involves:</font></p>

<ul>
    <li><font style="color:white;"> selected vCPU and memory specifications </font></li>
    <li><font style="color:white;"> System disk type and capacity </font></li>
    <li><font style="color:white;"> Internet bandwidth </font></li>
</ul>

<h2> Deployment Architecture </h2>

<p><img src="./img/deploy.png" alt=""/></p>

<h2> Parameter description </h2>

<table>
    <thead>
    <tr>
        <th><font style="color:white;"> parameter group </font></th>
        <th><font style="color:white;"> parameter items </font></th>
        <th><font style="color:white;"> Description </font></th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td><font style="color:white;"> Service instance </font></td>
        <td><font style="color:white;"> Service instance name </font></td>
        <td><font style="color:white;"> No more than 64 characters in length, must start with an English
            letter, and can contain numbers, English letters, dashes (-), and underscores (_)</font></td>
    </tr>
    <tr>
        <td></td>
        <td><font style="color:white;"> Region </font></td>
        <td><font style="color:white;"> Region where the service instance is deployed </font></td>
    </tr>
    <tr>
        <td></td>
        <td><font style="color:white;"> Payment type </font></td>
        <td><font style="color:white;"> Resource billing type: Pay-As-You-Go and Subscription </font></td>
    </tr>
    <tr>
        <td><font style="color:white;">ECS instance configuration </font></td>
        <td><font style="color:white;"> instance type </font></td>
        <td><font style="color:white;"> Instance specifications available in the Availability Zone </font>
        </td>
    </tr>
    <tr>
        <td></td>
        <td><font style="color:white;"> Instance password </font></td>
        <td><font style="color:white;"> is 8-30 in length and must contain three items (uppercase letters,
            lowercase letters, numbers, ()'~! @#$%^&*-+=<{}[]:;'<>,. special symbols in?/)</font></td>
    </tr>
    <tr>
        <td><font style="color:white;"> Network Configuration </font></td>
        <td><font style="color:white;"> Availability Zone </font></td>
        <td><font style="color:white;"> Zone where the ECS instance is located </font></td>
    </tr>
    <tr>
        <td></td>
        <td><font style="color:white;">VPC ID</font></td>
        <td><font style="color:white;"> VPC where the resource is located </font></td>
    </tr>
    <tr>
        <td></td>
        <td><font style="color:white;"> Switch ID</font></td>
        <td><font style="color:white;"> Switch where the resource is located </font></td>
    </tr>
    </tbody>
</table>

<h2> Deployment process </h2>

<ol>
    <li> visit the compute nest LobeChat<a
            href="https://computenest.console.aliyun.com/service/instance/create/default?type=user&ServiceName=LobeChat%E7%A4%BE%E5%8C%BA%E7%89%88">
        deployment link </a> and fill in the deployment parameters as prompted
    </li>
    <li> Fill in the instance parameters <img src="./img/param1.png" alt=""/></li>
    <li> Fill in the network parameters and click "Next: Confirm Order" <img src="./img/param2.png" alt=""/></li>
    <li> Click Create Now and wait for the service instance deployment to complete <img src="./img/param3.png" alt=""/>
    </li>
    <li> After the service instance is deployed, click the instance ID to go to the details page <img
            src="./img/serviceInstance1.png" alt=""/></li>
    <li> Use the URL to access the service instance <img src="./img/serviceInstance2.png" alt=""/></li>
    <li> Go to the LobeChat application interface and configure the API Key<img src="./img/lobechat.png" alt=""/></li>
    for the model.
    <li> Get started with LobeChat!</li>
</ol>
