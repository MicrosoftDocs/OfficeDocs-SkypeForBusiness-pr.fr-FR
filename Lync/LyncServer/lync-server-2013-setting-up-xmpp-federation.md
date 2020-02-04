---
title: 'Lync Server 2013 : Configuration de la fédération XMPP'
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
ms.openlocfilehash: fd61aded33d37e4a1f5f58e9050f3cd62794f9b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="b61c4-102">Configuration de la fédération XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b61c4-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b61c4-103">_**Dernière modification de la rubrique :** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="b61c4-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="b61c4-104">Pour déployer le proxy XMPP sur le serveur Edge, vous devez configurer le serveur Edge pour la Fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="b61c4-104">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation.</span></span> <span data-ttu-id="b61c4-105">Pour cela, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b61c4-105">To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="b61c4-106">Configuration de la Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="b61c4-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="b61c4-107">Ouvrez une session sur l’ordinateur sur lequel est installé l’Assistant Déploiement de Lync Server en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b61c4-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="b61c4-108">Sur le serveur frontal, ouvrez l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b61c4-108">On the Front End server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="b61c4-109">Cliquez sur installer ou mettre à jour le système serveur Lync, puis cliquez sur Configurer ou supprimer les composants Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b61c4-109">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="b61c4-110">Cliquez de nouveau sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="b61c4-110">Click Run Again.</span></span>

3.  <span data-ttu-id="b61c4-111">Dans configurer les composants serveur Lync, cliquez sur suivant.</span><span class="sxs-lookup"><span data-stu-id="b61c4-111">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="b61c4-112">L’écran de synthèse indique les actions à mesure qu’elles sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="b61c4-112">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="b61c4-113">Lorsque le déploiement est effectué, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles.</span><span class="sxs-lookup"><span data-stu-id="b61c4-113">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="b61c4-114">Cliquez sur Terminer pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="b61c4-114">Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="b61c4-115">Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b61c4-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="b61c4-116">Cliquez sur installer ou mettre à jour le système serveur Lync, puis cliquez sur Configurer ou supprimer les composants Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b61c4-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="b61c4-117">Cliquez de nouveau sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="b61c4-117">Click Run Again.</span></span>

5.  <span data-ttu-id="b61c4-118">Dans configurer les composants serveur Lync, cliquez sur suivant.</span><span class="sxs-lookup"><span data-stu-id="b61c4-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="b61c4-119">L’écran de synthèse indique les actions à mesure qu’elles sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="b61c4-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="b61c4-120">Lorsque le déploiement est effectué, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles.</span><span class="sxs-lookup"><span data-stu-id="b61c4-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="b61c4-121">Cliquez sur Terminer pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="b61c4-121">Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="b61c4-122">Sur le serveur Edge, dans l’Assistant Déploiement, en regard de l’étape 3 : demandez, installez ou attribuez des certificats, cliquez de nouveau sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="b61c4-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b61c4-123">Si vous déployez le serveur Edge pour la première fois, vous verrez exécuter au lieu de réexécuter.</span><span class="sxs-lookup"><span data-stu-id="b61c4-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="b61c4-124">Dans la page Tâches se rapportant aux certificats disponibles, cliquez sur Créer une demande de certificat.</span><span class="sxs-lookup"><span data-stu-id="b61c4-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="b61c4-125">Dans la page demande de certificat, cliquez sur certificat de bord externe.</span><span class="sxs-lookup"><span data-stu-id="b61c4-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="b61c4-126">Dans la page de demande retardée ou immédiate, activez la case à cocher préparer la demande maintenant, puis l’envoyer plus tard.</span><span class="sxs-lookup"><span data-stu-id="b61c4-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="b61c4-127">Dans la page fichier de demande de certificat, tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple,\\c\_:\_CERT l’Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="b61c4-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="b61c4-128">Dans la page spécifier un modèle de certificat secondaire, pour utiliser un modèle autre que le modèle par défaut du serveur Web, activez la case à cocher utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b61c4-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="b61c4-129">Dans la page Nom et paramètres de sécurité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b61c4-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="b61c4-130">Dans nom convivial, tapez un nom d’affichage pour le certificat.</span><span class="sxs-lookup"><span data-stu-id="b61c4-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="b61c4-131">En longueur, spécifiez la longueur en bits (en général, la valeur par défaut 2048)</span><span class="sxs-lookup"><span data-stu-id="b61c4-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="b61c4-132">Vérifier que la case à cocher marquer le certificat privé comme étant exportable est activée</span><span class="sxs-lookup"><span data-stu-id="b61c4-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="b61c4-133">Dans la page informations sur l’organisation, tapez le nom de l’organisation et celle de l’unité d’organisation (par exemple, une division ou un service).</span><span class="sxs-lookup"><span data-stu-id="b61c4-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="b61c4-134">Dans la page informations géographiques, spécifiez les informations d’emplacement</span><span class="sxs-lookup"><span data-stu-id="b61c4-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="b61c4-135">Sur la page nom de l’objet/nom de l’objet, les informations à remplir automatiquement par l’Assistant sont affichées.</span><span class="sxs-lookup"><span data-stu-id="b61c4-135">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="b61c4-136">Si d’autres noms d’objet sont nécessaires, vous pouvez les spécifier au cours des deux étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="b61c4-136">If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="b61c4-137">Dans la page Configuration du protocole SIP sur le nom de l’objet, activez la case à cocher Domain pour ajouter un SIP. \<entrée\> sipdomain dans la liste noms de remplacement de l’objet.</span><span class="sxs-lookup"><span data-stu-id="b61c4-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="b61c4-138">Dans la page configurez d’autres noms d’objet, spécifiez d’autres noms d’objet requis</span><span class="sxs-lookup"><span data-stu-id="b61c4-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b61c4-139">Si le proxy XMPP est installé, le nom de domaine par défaut (par exemple, contoso.com) est renseigné dans les entrées du SAN.</span><span class="sxs-lookup"><span data-stu-id="b61c4-139">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="b61c4-140">Si vous avez besoin d’entrées supplémentaires, ajoutez-les à cette étape.</span><span class="sxs-lookup"><span data-stu-id="b61c4-140">If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="b61c4-141">Dans la page Résumé de la demande, passez en revue les informations de certificat à utiliser pour générer la requête.</span><span class="sxs-lookup"><span data-stu-id="b61c4-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="b61c4-142">À la fin de l’exécution des commandes, vous pouvez consulter le journal ou cliquer sur suivant pour continuer.</span><span class="sxs-lookup"><span data-stu-id="b61c4-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="b61c4-143">Dans la page fichier de demande de certificat, vous pouvez afficher le fichier de demande de signature de certificat généré (CSR) en cliquant sur Afficher ou quitter l’Assistant Certificat en cliquant sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="b61c4-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="b61c4-144">Copiez le fichier de demande et envoyez-le à votre autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="b61c4-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="b61c4-145">Après avoir reçu, importé et attribué le certificat public, vous devez arrêter et redémarrer les services Edge Server.</span><span class="sxs-lookup"><span data-stu-id="b61c4-145">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="b61c4-146">Pour cela, entrez dans la console de gestion de Lync Server :</span><span class="sxs-lookup"><span data-stu-id="b61c4-146">You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="b61c4-147">Pour configurer le système DNS pour la Fédération XMPP, ajoutez l’enregistrement SRV suivant à DNS\_externe : XMPP-Server. \_TCP. \<nom de\> domaine l’enregistrement SRV sera résolu vers le nom de domaine complet d’accès du serveur Edge, avec une valeur de port de 5269.</span><span class="sxs-lookup"><span data-stu-id="b61c4-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="b61c4-148">Par ailleurs, vous configurez un enregistrement hôte « A » (par exemple, xmpp.contoso.com) qui pointe vers l’adresse IP du serveur Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="b61c4-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b61c4-149">Si vous disposez de pools de périphérie dans plusieurs sites, nous vous recommandons d’ajouter plusieurs enregistrements SRV pour la Fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="b61c4-149">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation.</span></span> <span data-ttu-id="b61c4-150">Ajoutez un enregistrement SRV pour chaque pool de périphérie de votre organisation et attribuez à chacun de ces enregistrements SRV une priorité différente.</span><span class="sxs-lookup"><span data-stu-id="b61c4-150">Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority.</span></span> <span data-ttu-id="b61c4-151">Lorsque tous les pools d’arêtes sont en cours d’exécution, les demandes XMPP seront gérées par le pool de bords avec la première priorité, mais si le pool de bords devient inactif, vous n’aurez pas besoin d’ajouter un nouvel enregistrement SRV pour restaurer la fonctionnalité de Fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="b61c4-151">When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="b61c4-152">Configurez une nouvelle stratégie d’accès externe pour permettre à tous les utilisateurs d’ouvrir Lync Server Management Shell sur le front end et de taper :</span><span class="sxs-lookup"><span data-stu-id="b61c4-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="b61c4-153">Activez l’accès XMPP pour les utilisateurs externes en entrant :</span><span class="sxs-lookup"><span data-stu-id="b61c4-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="b61c4-154">Sur le serveur Edge sur lequel est déployé le proxy XMPP, ouvrez une invite de commandes ou une interface de ligne de commande™ Windows PowerShell, puis tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b61c4-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="b61c4-155">La commande **netstat-ano** est une commande statistiques réseau, les paramètres **-ano** , qui affiche la totalité des connexions et des ports d’écoute, l’adresse et les ports sont affichés sous la forme d’une forme numérique et que l’ID du processus propriétaire est associé à chaque connexion.</span><span class="sxs-lookup"><span data-stu-id="b61c4-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="b61c4-156">Le caractère **|** définit un canal sur la commande suivante, **findstr**ou rechercher une chaîne.</span><span class="sxs-lookup"><span data-stu-id="b61c4-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="b61c4-157">Le nombre 5269 et 23456 transmis à FINDSTR en tant que paramètre indiquent à findstr d’effectuer une recherche dans la sortie de netstat pour les chaînes 5269 et 23456.</span><span class="sxs-lookup"><span data-stu-id="b61c4-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="b61c4-158">Si XMPP est configuré correctement, le résultat des commandes doit avoir pour effet d’écouter les connexions d’écoute et de connexion établie, à la fois sur les interfaces externes (port 5269) et internes (port 23456) du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b61c4-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="b61c4-159">Si les commandes ne renvoient pas de ports établis ou en écoute sur 5269 et 23456, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="b61c4-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="b61c4-160">Résoudre les problèmes de Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="b61c4-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="b61c4-161">Pour déterminer si le proxy XMPP est en cours d’exécution, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b61c4-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="b61c4-162">Ouvrez une session sur le serveur Edge qui exécute le service proxy XMPP en tant que membre du groupe de l’administrateur local.</span><span class="sxs-lookup"><span data-stu-id="b61c4-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="b61c4-163">Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Outils d’administration**, puis sur **services** .</span><span class="sxs-lookup"><span data-stu-id="b61c4-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="b61c4-164">Dans services, recherchez proxy Lync Server XMPP traduction de la passerelle proxy.</span><span class="sxs-lookup"><span data-stu-id="b61c4-164">In Services, locate Lync Server XMPP Translating Gateway Proxy.</span></span> <span data-ttu-id="b61c4-165">Le service doit être au mode **démarré** .</span><span class="sxs-lookup"><span data-stu-id="b61c4-165">The service should be in the **Started** state.</span></span> <span data-ttu-id="b61c4-166">Si ce n’est pas le cas, cliquez sur l’icône **Démarrer** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="b61c4-166">If it is not started, click the **Start** icon in the toolbar.</span></span> <span data-ttu-id="b61c4-167">L’icône s’affiche sous la forme d’une flèche verte vers la droite.</span><span class="sxs-lookup"><span data-stu-id="b61c4-167">The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="b61c4-168">Vérifiez que le service a changé pour **démarré**.</span><span class="sxs-lookup"><span data-stu-id="b61c4-168">Confirm that the service has changed to **Started**.</span></span> <span data-ttu-id="b61c4-169">Si le problème persiste, fermez les **services** et continuez.</span><span class="sxs-lookup"><span data-stu-id="b61c4-169">If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="b61c4-170">Si le service n’a pas réussi à démarrer, dans les outils d’administration, ouvrez l’observateur d’événements, puis référez-vous aux erreurs et avertissements dans la partie **serveur Lync** sous **journaux des applications et des services**.</span><span class="sxs-lookup"><span data-stu-id="b61c4-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="b61c4-171">Lorsque le service **passerelle de traduction de Lync Server XMPP** est en cours d’exécution, revérifiez les commandes netstat utilisées précédemment.</span><span class="sxs-lookup"><span data-stu-id="b61c4-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="b61c4-172">Si vous ne voyez pas les sessions établies ou écoutées, vérifiez et assurez-vous que l' **itinéraire de Fédération XMPP** est correctement configuré dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b61c4-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="b61c4-173">Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b61c4-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="b61c4-174">Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b61c4-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="b61c4-175">Dans le générateur de topologie, sélectionnez le site pour le routage de Fédération XMPP et l’avis pour vérifier que l’affectation de l’itinéraire de la **Fédération de site** pour la **Fédération XMPP** indique votre serveur Edge ou votre pool Edge en tant qu’attribution de l’itinéraire de Fédération XMPP sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b61c4-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="b61c4-176">Si l’affectation de l’itinéraire est incorrecte ou n’est pas définie, cliquez avec le bouton droit sur le site, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b61c4-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="b61c4-177">Activez la case à cocher Fédération XMPP, puis sélectionnez le serveur Edge ou le pool de bords approprié.</span><span class="sxs-lookup"><span data-stu-id="b61c4-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="b61c4-178">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="b61c4-178">Publish the topology.</span></span> <span data-ttu-id="b61c4-179">Pour plus d’informations, reportez-vous à [la rubrique publier votre topologie dans Lync Server 2013](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="b61c4-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b61c4-180">Même si ce n’est pas obligatoire et n’est généralement pas nécessaire, il est possible que vous deviez redémarrer les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="b61c4-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="b61c4-181">À l’aide du processus netstat utilisé précédemment, vérifiez que le serveur Edge écoute ou a établi des sessions sur le port 5269 et le port 23456.</span><span class="sxs-lookup"><span data-stu-id="b61c4-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="b61c4-182">Si vous ne voyez toujours pas les sessions attendues, consultez l’observateur d’événements pour connaître les causes possibles du problème de communication.</span><span class="sxs-lookup"><span data-stu-id="b61c4-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b61c4-183">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b61c4-183">See Also</span></span>


[<span data-ttu-id="b61c4-184">Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk</span><span class="sxs-lookup"><span data-stu-id="b61c4-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="b61c4-185">Gestion des partenaires fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b61c4-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

