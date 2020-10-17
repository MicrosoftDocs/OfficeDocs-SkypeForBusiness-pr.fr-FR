---
title: 'Lync Server 2013 : configuration de la Fédération XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cb6b2904ee2a8883c492e570173e73bc001cc03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497521"
---
# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="7d433-102">Configuration de la Fédération XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d433-102">Setting up XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d433-103">_**Dernière modification de la rubrique :** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="7d433-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="7d433-p101">Pour déployer le proxy XMPP sur le serveur Edge, vous devez configurer le serveur Edge pour la fédération XMPP. Pour cela, effectuez les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="7d433-p101">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation. To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="7d433-106">Configuration de la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="7d433-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="7d433-107">Ouvrez une session sur l’ordinateur sur lequel l’Assistant Déploiement de Lync Server est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7d433-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="7d433-p102">Sur le serveur frontal, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur Installer ou mettre à jour le système Lync Server, puis sur Installer ou supprimer des composants Lync Server. Cliquez sur Réexécuter.</span><span class="sxs-lookup"><span data-stu-id="7d433-p102">On the Front End server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

3.  <span data-ttu-id="7d433-p103">Dans Installer les composants Lync Server, cliquez sur Suivant. L’écran de résumé affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="7d433-p103">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="7d433-p104">Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur Installer ou mettre à jour le système Lync Server, puis sur Installer ou supprimer des composants Lync Server. Cliquez sur Réexécuter.</span><span class="sxs-lookup"><span data-stu-id="7d433-p104">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="7d433-p105">Dans Installer les composants Lync Server, cliquez sur Suivant. L’écran de résumé affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="7d433-p105">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="7d433-122">Sur le serveur Edge, dans l’Assistant Déploiement, en regard de Étape 3 : Demander, installer ou assigner les certificats, cliquez sur Réexécuter.</span><span class="sxs-lookup"><span data-stu-id="7d433-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="7d433-123">Si vous déployez le serveur Edge pour la première fois, Exécuter figure à la place de Réexécuter.</span><span class="sxs-lookup"><span data-stu-id="7d433-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="7d433-124">Dans la page Tâches se rapportant aux certificats disponibles, cliquez sur Créer une nouvelle demande de certificat.</span><span class="sxs-lookup"><span data-stu-id="7d433-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="7d433-125">Sur la page demande de certificat, cliquez sur certificat de serveur Edge externe.</span><span class="sxs-lookup"><span data-stu-id="7d433-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="7d433-126">Dans la page Demande différée ou immédiate, activez la case à cocher Préparer la demande maintenant, mais l’envoyer plus tard.</span><span class="sxs-lookup"><span data-stu-id="7d433-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="7d433-127">Dans la page fichier de demande de certificat, tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple, c : \\ CERT \_ exernal \_ Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="7d433-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="7d433-128">Dans la page Spécifier un autre modèle de certificat, pour utiliser un autre modèle que le modèle Serveur web par défaut, activez la case à cocher Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7d433-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="7d433-129">Dans la page Nom et paramètres de sécurité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7d433-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="7d433-130">Dans Nom convivial, tapez un nom d’affichage pour le certificat.</span><span class="sxs-lookup"><span data-stu-id="7d433-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="7d433-131">Dans Longueur en bits, spécifiez la longueur en bits (en général, la valeur par défaut est 2 048).</span><span class="sxs-lookup"><span data-stu-id="7d433-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="7d433-132">Vérifiez que la case à cocher Marquer la clé privée du certificat comme exportable est activée.</span><span class="sxs-lookup"><span data-stu-id="7d433-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="7d433-133">Dans la page Informations relatives à l’organisation, tapez le nom de l’organisation et de l’unité d’organisation (par exemple, une division ou un service).</span><span class="sxs-lookup"><span data-stu-id="7d433-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="7d433-134">Dans la page Informations géographiques, spécifiez les informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="7d433-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="7d433-p106">Dans la page Nom du sujet/Autres noms du sujet, le système affiche les informations automatiquement renseignées par l’Assistant. Si d’autres noms du sujet doivent être ajoutés, spécifiez-les lors des deux étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="7d433-p106">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="7d433-137">Sur la page paramètre du domaine SIP sur les autres noms du sujet, activez la case à cocher domaine pour ajouter un SIP.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="7d433-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="7d433-138">entrée de la liste des autres noms du sujet.</span><span class="sxs-lookup"><span data-stu-id="7d433-138">entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="7d433-139">Dans la page Configurer d’autres noms du sujet supplémentaires, spécifiez les autres noms du sujet supplémentaires requis.</span><span class="sxs-lookup"><span data-stu-id="7d433-139">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="7d433-p108">Si le proxy XMPP est installé, par défaut, les entrées SAN sont remplies avec le nom de domaine (par exemple, contoso.com). Si vous avez besoin d’entrées supplémentaires, ajoutez-les dans cette étape.</span><span class="sxs-lookup"><span data-stu-id="7d433-p108">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="7d433-142">Dans la page Résumé de la demande, vérifiez les informations de certificat à utiliser pour générer la demande.</span><span class="sxs-lookup"><span data-stu-id="7d433-142">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="7d433-143">Une fois l’exécution des commandes terminée, vous pouvez afficher le journal ou cliquer sur Suivant pour continuer.</span><span class="sxs-lookup"><span data-stu-id="7d433-143">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="7d433-144">Dans la page Fichier de demande de certificat, vous pouvez afficher le fichier de demande de signature de certificat (CSR) généré en cliquant sur Afficher ou quitter l’Assistant Certificat en cliquant sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="7d433-144">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="7d433-145">Copiez le fichier de demande et envoyez-le à l’autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="7d433-145">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="7d433-p109">Après la réception, l’importation et l’affectation du certificat public, vous devez redémarrer les services du serveur Edge. Pour cela, tapez dans la console de gestion Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d433-p109">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="7d433-148">Pour configurer DNS pour la Fédération XMPP, vous devez ajouter l’enregistrement SRV suivant à DNS externe : \_ XMPP-Server. \_ TCP.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="7d433-148">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="7d433-149">L’enregistrement SRV est résolu en un nom de domaine complet du serveur Edge d’accès, avec une valeur de port de 5269.</span><span class="sxs-lookup"><span data-stu-id="7d433-149">The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="7d433-150">Par ailleurs, vous devez configurer un enregistrement d’hôte « A » (par exemple, xmpp.contoso.com) qui pointe vers l’adresse IP du serveur Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="7d433-150">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7d433-p111">Si vous avez des pools de serveurs Edge dans plusieurs sites, nous vous recommandons d’ajouter plusieurs enregistrements SRV pour la fédération XMPP. Ajoutez un enregistrement SRV pour chaque pool de serveurs Edge dans votre organisation, puis donnez à chacun de ces enregistrements SRV une priorité différente. Lorsque tous les pools de serveurs Edge sont en cours d’exécution, les demandes XMPP sont toutes traitées par le pool de serveurs Edge de première priorité. Toutefois, si ce pool de serveurs Edge tombe en panne, vous n’êtes pas obligé d’ajouter un enregistrement SRV pour rétablir les fonctionnalités de fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="7d433-p111">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation. Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority. When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="7d433-154">Configurez une nouvelle stratégie d’accès externe pour activer tous les utilisateurs en ouvrant Lync Server Management Shell sur le serveur frontal et en tapant :</span><span class="sxs-lookup"><span data-stu-id="7d433-154">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="7d433-155">Activez l’accès XMPP pour les utilisateurs externes en tapant :</span><span class="sxs-lookup"><span data-stu-id="7d433-155">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="7d433-156">Sur le serveur Edge sur lequel le proxy XMPP est déployé, ouvrez une invite de commandes ou une interface de ligne de commande™ Windows PowerShell, puis tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="7d433-156">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="7d433-157">La commande **netstat –ano** est une commande de statistiques réseau, la paramètres **–ano** demandent que netstat affiche la totalité des connexions et des ports d’écoute, que l’adresse et les ports soient affichés sous forme numérique, et que l’ID du processus propriétaire soit associé à chaque connexion.</span><span class="sxs-lookup"><span data-stu-id="7d433-157">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="7d433-158">Le caractère **|** définit un canal pour la commande suivante, **findstr**ou rechercher une chaîne.</span><span class="sxs-lookup"><span data-stu-id="7d433-158">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="7d433-159">Le nombre 5269 et 23456 transmis à FINDSTR en tant que paramètre demande à findstr de rechercher la sortie de netstat pour les chaînes 5269 et 23456.</span><span class="sxs-lookup"><span data-stu-id="7d433-159">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="7d433-160">Si XMPP est correctement configuré, le résultat des commandes doit aboutir à des connexions d’écoute et établies, à la fois sur les interfaces externe (port 5269) et interne (port 23456) du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="7d433-160">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="7d433-161">Si les commandes ne retournent pas des ports établis ou d’écoute sur 5269 et 23456, examinez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="7d433-161">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="7d433-162">Dépannage de la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="7d433-162">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="7d433-163">Pour déterminer si le proxy XMPP est en cours d’exécution, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7d433-163">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="7d433-164">Ouvrez une session sur le serveur Edge qui exécute le service proxy XMPP en tant que membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="7d433-164">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="7d433-165">Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Outils d’administration**, puis sur **Services**.</span><span class="sxs-lookup"><span data-stu-id="7d433-165">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="7d433-p113">Dans Services, recherchez Proxy de passerelle de traduction XMPP de Lync Server. Le service doit avoir l’état **Démarré**. S’il n’est pas démarré, cliquez sur l’icône **Démarrer** dans la barre d’outils. L’icône apparaît sous la forme d’une flèche verte pointant vers la droite.</span><span class="sxs-lookup"><span data-stu-id="7d433-p113">In Services, locate Lync Server XMPP Translating Gateway Proxy. The service should be in the **Started** state. If it is not started, click the **Start** icon in the toolbar. The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="7d433-p114">Confirmez que le service a bien l’état **Démarré**. S’il a correctement démarré, fermez **Services** et continuez.</span><span class="sxs-lookup"><span data-stu-id="7d433-p114">Confirm that the service has changed to **Started**. If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="7d433-172">Si le service n’a pas correctement démarré, dans Outils d’administration, ouvrez l’observateur d’événements et passez en revue les erreurs et les avertissements contenus dans la partie **Lync Server** sous **Journaux des applications et des services**.</span><span class="sxs-lookup"><span data-stu-id="7d433-172">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="7d433-173">Une fois que le service **Passerelle de traduction XMPP de Lync Server** est en cours d’exécution, revérifiez les commandes netstat utilisées précédemment.</span><span class="sxs-lookup"><span data-stu-id="7d433-173">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="7d433-174">Si vous ne voyez pas les sessions établies ou écoutées, vérifiez et assurez-vous que l' **itinéraire de Fédération XMPP** est correctement configuré dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="7d433-174">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="7d433-175">Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7d433-175">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="7d433-176">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7d433-176">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="7d433-177">Dans le générateur de topologies, sélectionnez le site pour l’itinéraire de Fédération XMPP et vérifiez que l’attribution de l' **itinéraire de Fédération du site** pour la **Fédération XMPP** indique votre serveur Edge ou pool de serveurs Edge comme l’attribution de l’itinéraire de Fédération XMPP sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7d433-177">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="7d433-178">Si l’attribution de l’itinéraire est incorrecte ou n’est pas définie, cliquez avec le bouton droit sur le site, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7d433-178">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="7d433-179">Activez la case à cocher Fédération XMPP, puis sélectionnez le serveur Edge ou le pool de serveurs Edge correct.</span><span class="sxs-lookup"><span data-stu-id="7d433-179">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="7d433-180">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="7d433-180">Publish the topology.</span></span> <span data-ttu-id="7d433-181">Pour plus d’informations, reportez-vous à [publier votre topologie dans Lync Server 2013](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="7d433-181">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="7d433-182">Bien que cela ne soit pas obligatoire et généralement inutile, vous devrez peut-être redémarrer les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="7d433-182">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="7d433-183">À l’aide du processus netstat utilisé précédemment, vérifiez que le serveur Edge écoute ou a des sessions établies sur le port 5269 et le port 23456.</span><span class="sxs-lookup"><span data-stu-id="7d433-183">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="7d433-184">Si vous ne voyez toujours pas les sessions attendues, passez en revue l’observateur d’événements pour tenter de trouver les causes possibles de ce problème de communication.</span><span class="sxs-lookup"><span data-stu-id="7d433-184">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d433-185">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d433-185">See Also</span></span>


[<span data-ttu-id="7d433-186">Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk</span><span class="sxs-lookup"><span data-stu-id="7d433-186">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="7d433-187">Gérer les partenaires fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d433-187">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

