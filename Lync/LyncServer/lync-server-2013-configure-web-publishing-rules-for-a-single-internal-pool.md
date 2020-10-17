---
title: 'Lync Server 2013 : configuration des règles de publication Web pour un pool interne unique'
description: 'Lync Server 2013 : configurez les règles de publication Web pour un pool interne unique.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45015c90fdac92fb488affc871f2cfaf9d7506a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560510"
---
# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="99bad-103">Configurer des règles de publication Web pour un pool interne unique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99bad-103">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99bad-104">_**Dernière modification de la rubrique :** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="99bad-104">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="99bad-105">Microsoft Forefront Threat Management Gateway 2010 et Internet Information Server application Request Routing (IIS ARR) utilise des règles de publication Web pour publier des ressources internes, telles qu’une URL de réunion, aux utilisateurs sur Internet.</span><span class="sxs-lookup"><span data-stu-id="99bad-105">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="99bad-106">En plus des URL des services Web pour les répertoires virtuels, vous devez également créer des règles de publication pour les URL simples, l’URL LyncDiscover et le serveur Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="99bad-106">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="99bad-107">Pour chaque URL simple, vous devez créer une règle individuelle sur le proxy inverse qui pointe sur cette URL simple.</span><span class="sxs-lookup"><span data-stu-id="99bad-107">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="99bad-108">Si vous déployez la mobilité et que vous utilisez la découverte automatique, vous devez créer une règle de publication pour l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="99bad-108">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="99bad-109">La découverte automatique requiert également des règles de publication pour l’URL des services Web Lync Server externes pour votre pool directeur et votre pool frontal.</span><span class="sxs-lookup"><span data-stu-id="99bad-109">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="99bad-110">Pour plus d’informations sur la création des règles de publication Web pour la découverte automatique, voir [configuration du proxy inverse pour la mobilité dans Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="99bad-110">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="99bad-111">Suivez les procédures ci-dessous pour créer des règles de publication web.</span><span class="sxs-lookup"><span data-stu-id="99bad-111">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99bad-112">Ces procédures supposent que vous avez installé l’édition standard de Forefront Threat Management Gateway (TMG) 2010 ou que vous avez installé et configuré Internet Information Server avec l’extension de routage des demandes d’application (IIS ARR).</span><span class="sxs-lookup"><span data-stu-id="99bad-112">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="99bad-113">Vous utilisez TMG ou IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="99bad-113">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="99bad-114">Pour créer une règle de publication de serveur web sur l’ordinateur qui exécute TMG 2010</span><span class="sxs-lookup"><span data-stu-id="99bad-114">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="99bad-115">Cliquez sur **Démarrer**, sélectionnez **Programmes**, **Microsoft Forefront TMG**, puis cliquez sur **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="99bad-115">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="99bad-116">Dans le volet de gauche, développez **NomServeur**, cliquez avec le bouton droit sur **Stratégie de pare-feu**, sélectionnez **Nouveau**, puis cliquez sur **Règle de publication web**.</span><span class="sxs-lookup"><span data-stu-id="99bad-116">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="99bad-117">Dans la page **Assistant Nouvelle règle de publication web**, entrez un nom convivial pour la règle de publication (par exemple, LyncServerWebDownloadsRule).</span><span class="sxs-lookup"><span data-stu-id="99bad-117">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="99bad-118">Dans la page **Sélectionner l’action de la règle**, sélectionnez **Autoriser**.</span><span class="sxs-lookup"><span data-stu-id="99bad-118">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="99bad-119">Dans la page **Type de publication**, sélectionnez **Publier un seul site web ou équilibreur de charge**.</span><span class="sxs-lookup"><span data-stu-id="99bad-119">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="99bad-120">Dans la page **Sécurité de connexion serveur**, sélectionnez **Utiliser SSL pour se connecter au serveur web publié ou à la batterie de serveurs**.</span><span class="sxs-lookup"><span data-stu-id="99bad-120">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="99bad-121">Dans la page **Détails de publication interne**, tapez le nom de domaine complet de la batterie de serveurs web internes qui héberge le contenu de réunion et les fichiers de carnet d’adresses dans la zone **Nom du site interne**.</span><span class="sxs-lookup"><span data-stu-id="99bad-121">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99bad-122">Si votre serveur interne est un serveur Standard Edition, ce nom de domaine complet est celui du serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="99bad-122">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="99bad-123">Si votre serveur interne est un pool frontal, le nom de domaine complet (FQDN) est une adresse IP virtuelle (VIP) de l’équilibreur de la charge matérielle qui équilibre la charge des serveurs de la batterie de serveurs web internes.</span><span class="sxs-lookup"><span data-stu-id="99bad-123">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="99bad-124">Le serveur TMG doit pouvoir résoudre le nom de domaine complet sur l’adresse IP du serveur web interne.</span><span class="sxs-lookup"><span data-stu-id="99bad-124">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="99bad-125">Si le serveur TMG ne parvient pas à résoudre le nom de domaine complet (FQDN) en adresse IP correcte, vous pouvez sélectionner <STRONG>utiliser un nom d’ordinateur ou une adresse IP pour se connecter au serveur publié</STRONG>, puis, dans la zone nom de l' <STRONG>ordinateur ou</STRONG> <STRONG>adresse IP</STRONG> , tapez l’adresse IP du serveur Web interne.</span><span class="sxs-lookup"><span data-stu-id="99bad-125">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="99bad-126">Dans ce cas, vous devez vous assurer que le port 53 est ouvert sur le serveur TMG et que celui-ci parvient à atteindre un serveur DNS résidant dans le réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="99bad-126">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="99bad-127">Vous pouvez également utiliser des entrées dans le fichier hôtes local pour permettre la résolution des noms.</span><span class="sxs-lookup"><span data-stu-id="99bad-127">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="99bad-128">Sur la page **Détails de publication interne** , dans la zone **chemin d’accès (facultatif)** , tapez **/\*** comme chemin d’accès du dossier à publier.</span><span class="sxs-lookup"><span data-stu-id="99bad-128">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99bad-p105">Dans l’Assistant de publication de sites web, vous ne pouvez indiquer qu’un seul chemin d’accès. Vous pouvez toutefois en ajouter d’autres en modifiant les propriétés de la règle.</span><span class="sxs-lookup"><span data-stu-id="99bad-p105">In the website publishing wizard you can only specify one path. Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="99bad-131">Dans la page **Informations sur les noms publics**, confirmez que **Ce nom de domaine** est bien sélectionné sous **Accepter les demandes pour**, et tapez le nom de domaine complet des services web externes dans la zone **Nom public**.</span><span class="sxs-lookup"><span data-stu-id="99bad-131">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="99bad-132">Dans la page **Sélectionnez le port d’écoute**, cliquez sur **Nouveau** pour ouvrir l’Assistant Nouvelle définition de port d’écoute web.</span><span class="sxs-lookup"><span data-stu-id="99bad-132">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="99bad-133">Dans la page **Assistant Nouveau port d’écoute web**, tapez le nom du port d’écoute web dans la zone **Nom du port d’écoute web** (par exemple, LyncServerWebServers).</span><span class="sxs-lookup"><span data-stu-id="99bad-133">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="99bad-134">Dans la page **Sécurité de la connexion client**, sélectionnez **Exiger des connexions sécurisées SSL avec les clients**.</span><span class="sxs-lookup"><span data-stu-id="99bad-134">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="99bad-135">Dans la page **Adresse IP de l’écouteur web**, sélectionnez **Externe**, puis cliquez sur **Sélectionner l’adresse IP**.</span><span class="sxs-lookup"><span data-stu-id="99bad-135">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="99bad-136">Dans la page **Sélection de l’adresse IP de l’écouteur externe**, sélectionnez **Les adresses IP spécifiées inscrites sur l’ordinateur Forefront TMG** qui sont dans le réseau sélectionné, sélectionnez l’adresse IP appropriée, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="99bad-136">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="99bad-137">Dans la page **Certificats SSL de l’écouteur**, sélectionnez **Affecter un certificat à chaque adresse IP**, sélectionnez l’adresse IP associée au nom de domaine web complet externe, puis cliquez sur **Sélectionner le certificat**.</span><span class="sxs-lookup"><span data-stu-id="99bad-137">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="99bad-138">Dans la page **Sélectionner le certificat**, sélectionnez le certificat qui correspond aux noms publics spécifiés à l’étape 9, puis cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="99bad-138">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="99bad-139">Dans la page **Paramètre d’authentification**, sélectionnez **Pas d’authentification**.</span><span class="sxs-lookup"><span data-stu-id="99bad-139">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="99bad-140">Dans la page **Paramètres de l’authentification unique**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="99bad-140">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="99bad-141">Dans la page **Fin de l’Assistant Nouveau port d’écoute web**, vérifiez que les paramètres du **port d’écoute web** sont corrects, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="99bad-141">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="99bad-142">Dans la page **Délégation de l’authentification**, sélectionnez **Aucune délégation pour laisser le client s’authentifier directement**.</span><span class="sxs-lookup"><span data-stu-id="99bad-142">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="99bad-143">Dans la page **Ensemble d’utilisateurs**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="99bad-143">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="99bad-144">Dans la page **Fin de l’Assistant Nouvelle règle de publication web**, vérifiez que les paramètres de la règle de publication web sont corrects, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="99bad-144">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="99bad-145">Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.</span><span class="sxs-lookup"><span data-stu-id="99bad-145">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="99bad-146">Pour créer une règle de publication de serveur Web sur l’ordinateur qui exécute IIS ARR</span><span class="sxs-lookup"><span data-stu-id="99bad-146">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="99bad-147">Liez le certificat que vous allez utiliser pour le proxy inverse au protocole HTTPs.</span><span class="sxs-lookup"><span data-stu-id="99bad-147">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="99bad-148">Cliquez sur **Démarrer**, sélectionnez **programmes**, **Outils d’administration**, puis **Gestionnaire des services Internet (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="99bad-148">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99bad-149">Une aide supplémentaire, des captures d’écran et des conseils sur le déploiement et la configuration d’IIS ARR se trouve dans l’article NextHop <A href="https://go.microsoft.com/fwlink/?linkid=293391">à l’aide d’IIS ARR en tant que proxy inverse pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="99bad-149">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="https://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="99bad-150">Si vous ne l’avez pas déjà fait, importez le certificat que vous utiliserez pour le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="99bad-150">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="99bad-151">Dans le **Gestionnaire des services Internet (IIS)**, cliquez sur le nom du serveur proxy inverse dans la partie gauche de la console.</span><span class="sxs-lookup"><span data-stu-id="99bad-151">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="99bad-152">Au milieu de la console, sous **IIS** , localisez les **certificats de serveur**.</span><span class="sxs-lookup"><span data-stu-id="99bad-152">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="99bad-153">Cliquez avec le bouton droit sur **certificats de serveur** , puis sélectionnez **ouvrir la fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="99bad-153">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="99bad-154">Sur le côté droit de la console, cliquez sur **Importer...**.</span><span class="sxs-lookup"><span data-stu-id="99bad-154">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="99bad-155">Tapez le chemin d’accès et le nom de fichier du certificat avec l’extension, ou cliquez sur **...**</span><span class="sxs-lookup"><span data-stu-id="99bad-155">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="99bad-156">pour rechercher le certificat.</span><span class="sxs-lookup"><span data-stu-id="99bad-156">to browse for the certificate.</span></span> <span data-ttu-id="99bad-157">Sélectionnez le certificat, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="99bad-157">Select the certificate and click **Open**.</span></span> <span data-ttu-id="99bad-158">Fournissez le mot de passe utilisé pour protéger la clé privée (si vous avez attribué un mot de passe lors de l’exportation du certificat et de la clé privée).</span><span class="sxs-lookup"><span data-stu-id="99bad-158">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="99bad-159">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="99bad-159">Click **OK**.</span></span> <span data-ttu-id="99bad-160">Si l’importation de certificat a réussi, le certificat apparaît sous la forme d’une entrée au milieu de la console sous forme d’entrée dans les **certificats de serveur**.</span><span class="sxs-lookup"><span data-stu-id="99bad-160">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="99bad-161">Affectez le certificat pour une utilisation par HTTPs.</span><span class="sxs-lookup"><span data-stu-id="99bad-161">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="99bad-162">Sur le côté gauche de la console, sélectionnez le **site Web par défaut** du serveur IIS.</span><span class="sxs-lookup"><span data-stu-id="99bad-162">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="99bad-163">Sur le côté droit, cliquez sur **liaisons...**.</span><span class="sxs-lookup"><span data-stu-id="99bad-163">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="99bad-164">Dans la boîte de dialogue **liaisons de site** , cliquez sur **Ajouter.**...</span><span class="sxs-lookup"><span data-stu-id="99bad-164">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="99bad-165">Dans la boîte de dialogue **Ajouter une liaison de site** , sous **type :**, sélectionnez **https**.</span><span class="sxs-lookup"><span data-stu-id="99bad-165">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="99bad-166">La sélection du protocole HTTPS vous permet de sélectionner le certificat à utiliser pour HTTPS.</span><span class="sxs-lookup"><span data-stu-id="99bad-166">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="99bad-167">Sous **certificat SSL :**, sélectionnez le certificat que vous avez importé pour le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="99bad-167">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="99bad-168">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="99bad-168">Click **OK**.</span></span> <span data-ttu-id="99bad-169">Ensuite, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="99bad-169">Then, click **Close**.</span></span> <span data-ttu-id="99bad-170">Le certificat est maintenant lié au proxy inverse pour SSL (Secure Socket Layer) et TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="99bad-170">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="99bad-171">Si vous recevez un avertissement lorsque vous fermez les boîtes de dialogue de liaison pour lesquelles des certificats intermédiaires sont manquants, vous devez rechercher et importer le certificat d’autorité racine de l’autorité de certification publique et tous les certificats de l’autorité de certification intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="99bad-171">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="99bad-172">Consultez les instructions de l’autorité de certification publique à partir de laquelle vous avez demandé votre certificat et suivez les instructions pour demander et importer une chaîne de certificats.</span><span class="sxs-lookup"><span data-stu-id="99bad-172">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="99bad-173">Si vous avez exporté le certificat à partir de votre serveur Edge, vous pouvez exporter le certificat de l’autorité de certification racine et tous les certificats de l’autorité de certification intermédiaire associés au serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="99bad-173">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="99bad-174">Importez le certificat d’autorité de certification racine dans le magasin d’autorités de certification racines de confiance et les certificats intermédiaires dans le magasin d’autorités de certification intermédiaires de l’ordinateur (à ne pas confondre avec le magasin d’utilisateurs).</span><span class="sxs-lookup"><span data-stu-id="99bad-174">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="99bad-175">Sur le côté gauche de la console, sous le nom du serveur IIS, cliquez avec le bouton droit sur **batteries de serveurs** , puis cliquez sur créer une **batterie de serveurs...**.</span><span class="sxs-lookup"><span data-stu-id="99bad-175">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99bad-176">Si vous ne voyez pas le nœud <STRONG>batteries de serveurs</STRONG> , vous devez installer le routage des demandes d’applications.</span><span class="sxs-lookup"><span data-stu-id="99bad-176">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="99bad-177">Pour plus d’informations, voir <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up Reverse Proxy Servers for Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="99bad-177">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="99bad-178">Dans la boîte de dialogue **créer une batterie** de serveurs, dans nom de la **batterie de serveurs**, tapez le nom (il peut s’agir d’un nom convivial pour l’identification) pour la première URL.</span><span class="sxs-lookup"><span data-stu-id="99bad-178">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="99bad-179">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="99bad-179">Click **Next**.</span></span>

6.  <span data-ttu-id="99bad-180">Dans la boîte de dialogue **Ajouter un serveur** dans **adresse du serveur**, tapez le nom de domaine complet (FQDN) des services Web externes sur votre serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="99bad-180">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="99bad-181">Les noms qui seront utilisés ici à titre d’exemple sont les mêmes que ceux utilisés dans la section de planification pour le proxy inverse, [Certificate Summary-Reverse Proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="99bad-181">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="99bad-182">En vous référant à la planification du proxy inverse, nous allons taper le nom de domaine complet `webext.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="99bad-182">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="99bad-183">Vérifiez que la case à cocher en regard de **en ligne** est activée.</span><span class="sxs-lookup"><span data-stu-id="99bad-183">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="99bad-184">Cliquez sur **Ajouter** pour ajouter le serveur au pool de serveurs Web pour cette configuration.</span><span class="sxs-lookup"><span data-stu-id="99bad-184">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="99bad-185">Lync Server utilise des programmes d’équilibrage de la charge matérielle pour le directeur de pool et les serveurs frontaux pour le trafic HTTP et HTTPs.</span><span class="sxs-lookup"><span data-stu-id="99bad-185">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="99bad-186">Vous ne fournissez qu’un seul nom de domaine complet lors de l’ajout d’un serveur à la batterie de serveurs IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="99bad-186">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="99bad-187">Le nom de domaine complet sera le serveur frontal ou le directeur dans les configurations de serveur non regroupé, ou le nom de domaine complet (FQDN) de l’équilibreur de charge matérielle configuré pour les pools de serveurs.</span><span class="sxs-lookup"><span data-stu-id="99bad-187">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="99bad-188">La seule méthode prise en charge pour équilibrer la charge du trafic HTTP et HTTPs consiste à utiliser des programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="99bad-188">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="99bad-189">Dans la boîte de dialogue **Ajouter un serveur** , cliquez sur **Paramètres avancés.**...</span><span class="sxs-lookup"><span data-stu-id="99bad-189">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="99bad-190">Une boîte de dialogue s’ouvre pour définir le routage de demande d’application pour les demandes au nom de domaine complet configuré.</span><span class="sxs-lookup"><span data-stu-id="99bad-190">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="99bad-191">L’objectif est de redéfinir le port utilisé lorsque la demande est traitée par IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="99bad-191">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="99bad-192">Par défaut, le port HTTP de destination doit être défini comme 8080.</span><span class="sxs-lookup"><span data-stu-id="99bad-192">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="99bad-193">Cliquez sur en regard de la **httpPort 80** actuelle et définissez la valeur sur **8080**.</span><span class="sxs-lookup"><span data-stu-id="99bad-193">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="99bad-194">Cliquez sur en regard de la **httpsPort 443** actuelle et définissez la valeur sur **4443**.</span><span class="sxs-lookup"><span data-stu-id="99bad-194">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="99bad-195">Laissez le paramètre **Weight** à 100.</span><span class="sxs-lookup"><span data-stu-id="99bad-195">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="99bad-196">Si nécessaire, vous pouvez redéfinir les pondérations d’une règle donnée une fois que vous avez défini les statistiques de la planification.</span><span class="sxs-lookup"><span data-stu-id="99bad-196">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="99bad-197">Cliquez sur **Terminer** pour terminer cette partie de la configuration de la règle.</span><span class="sxs-lookup"><span data-stu-id="99bad-197">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="99bad-198">Vous pouvez voir une boîte de dialogue de réécriture de règles qui vous informe que le gestionnaire des services Internet (IIS) peut créer une règle de réécriture d’URL pour acheminer automatiquement toutes les demandes entrantes vers la batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="99bad-198">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="99bad-199">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="99bad-199">Click **Yes**.</span></span> <span data-ttu-id="99bad-200">Vous allez ajuster les règles manuellement, mais la sélection de Oui définit la configuration initiale..</span><span class="sxs-lookup"><span data-stu-id="99bad-200">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="99bad-201">Cliquez sur le nom de la batterie de serveurs que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="99bad-201">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="99bad-202">Sous **batterie de serveurs** dans l’affichage fonctionnalités du gestionnaire des services Internet (IIS), vous double-cliquez sur **mise en cache**.</span><span class="sxs-lookup"><span data-stu-id="99bad-202">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="99bad-203">Désactivez l’option **activer le cache disque**.</span><span class="sxs-lookup"><span data-stu-id="99bad-203">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="99bad-204">Cliquez sur **appliquer** à droite.</span><span class="sxs-lookup"><span data-stu-id="99bad-204">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="99bad-205">Cliquez sur le nom de la batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="99bad-205">Click the name of the server farm.</span></span> <span data-ttu-id="99bad-206">Sous **batterie de serveurs** dans l’affichage fonctionnalités du gestionnaire des services Internet (IIS), vous double-cliquez sur **proxy**.</span><span class="sxs-lookup"><span data-stu-id="99bad-206">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="99bad-207">Dans la page Paramètres du proxy, modifiez la valeur du délai d’expiration **(secondes)** en fonction de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="99bad-207">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="99bad-208">Cliquez sur **appliquer** pour enregistrer la modification.</span><span class="sxs-lookup"><span data-stu-id="99bad-208">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="99bad-209">La valeur du délai d’expiration du proxy est un nombre qui varie d’un déploiement à l’autre.</span><span class="sxs-lookup"><span data-stu-id="99bad-209">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="99bad-210">Vous devez surveiller votre déploiement et modifier la valeur pour la meilleure expérience pour les clients.</span><span class="sxs-lookup"><span data-stu-id="99bad-210">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="99bad-211">Vous pouvez définir la valeur sur 200.</span><span class="sxs-lookup"><span data-stu-id="99bad-211">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="99bad-212">Si vous prenez en charge les clients mobiles Lync dans votre environnement, vous devez définir la valeur sur 960 pour autoriser le délai d’expiration des notifications de type transmission à partir d’Office 365, dont la valeur de délai d’expiration est de 900.</span><span class="sxs-lookup"><span data-stu-id="99bad-212">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="99bad-213">Il est fort probable que vous deviez augmenter la valeur du délai d’expiration pour éviter que le client se déconnecte lorsque la valeur est trop faible ou réduire le nombre si les connexions par le proxy ne se déconnectent pas et s’effacent longtemps après la déconnexion du client.</span><span class="sxs-lookup"><span data-stu-id="99bad-213">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="99bad-214">Surveillance et base-la définition de la normale pour votre environnement est la seule façon de déterminer où se trouve le paramètre correct pour cette valeur.</span><span class="sxs-lookup"><span data-stu-id="99bad-214">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="99bad-215">Cliquez sur le nom de la batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="99bad-215">Click the name of the server farm.</span></span> <span data-ttu-id="99bad-216">Sous **batterie de serveurs** dans l’affichage fonctionnalités du gestionnaire des services Internet (IIS), vous double-cliquez sur **règles de routage**.</span><span class="sxs-lookup"><span data-stu-id="99bad-216">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="99bad-217">Dans la boîte de dialogue Règles de routage, sous routage, désactivez la case à cocher en regard de activer le déchargement SSL.</span><span class="sxs-lookup"><span data-stu-id="99bad-217">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="99bad-218">Si la désactivation de cette case n’est pas disponible, activez la case à cocher **utiliser la réécriture d’URL pour inspecter les demandes entrantes**.</span><span class="sxs-lookup"><span data-stu-id="99bad-218">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="99bad-219">Cliquez sur **appliquer** pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="99bad-219">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="99bad-220">Le déchargement SSL par le proxy inverse n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="99bad-220">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="99bad-221">Répétez les étapes 5-11 pour chaque URL qui doit transiter par le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="99bad-221">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="99bad-222">Une liste commune est la suivante :</span><span class="sxs-lookup"><span data-stu-id="99bad-222">A common list would be the following:</span></span>
    
      - <span data-ttu-id="99bad-223">Services Web de serveur frontal externes : webext.contoso.com (déjà configurés par la visite initiale)</span><span class="sxs-lookup"><span data-stu-id="99bad-223">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="99bad-224">Services Web Director externes pour Director : webdirext.contoso.com (facultatif si un directeur est déployé)</span><span class="sxs-lookup"><span data-stu-id="99bad-224">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="99bad-225">URL simple : meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="99bad-225">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="99bad-226">Numérotation URL simple : dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="99bad-226">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="99bad-227">URL de découverte automatique Lync : lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="99bad-227">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="99bad-228">URL d’Office Web Apps Server : officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="99bad-228">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="99bad-229">L’URL du serveur Office Web Apps Server utilisera une autre adresse httpsPort.</span><span class="sxs-lookup"><span data-stu-id="99bad-229">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="99bad-230">À l’étape 7, vous définissez le <STRONG>httpsPort</STRONG> en tant que <STRONG>443</STRONG> et le <STRONG>httpPort</STRONG> en tant que port <STRONG>80</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="99bad-230">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="99bad-231">Tous les autres paramètres de configuration sont les mêmes.</span><span class="sxs-lookup"><span data-stu-id="99bad-231">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="99bad-232">Sur le côté gauche de la console, cliquez sur le nom du serveur IIS.</span><span class="sxs-lookup"><span data-stu-id="99bad-232">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="99bad-233">Au milieu de la console, recherchez **URL Rewrite** sous **IIS**.</span><span class="sxs-lookup"><span data-stu-id="99bad-233">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="99bad-234">Double-cliquez sur réécriture d’URL pour ouvrir la configuration des règles de réécriture d’URL.</span><span class="sxs-lookup"><span data-stu-id="99bad-234">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="99bad-235">Vous devez voir les règles pour chaque batterie de serveurs que vous avez créée lors des étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="99bad-235">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="99bad-236">Si vous ne le faites pas, vérifiez que vous avez cliqué sur le nom du **serveur IIS** juste en dessous du nœud de la **page de démarrage** dans la console du gestionnaire Internet Information Server.</span><span class="sxs-lookup"><span data-stu-id="99bad-236">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="99bad-237">Dans la boîte de dialogue de **réécriture d’URL** , à l’aide de webext.contoso.com comme exemple, le nom complet de la règle tel qu’il est affiché est **arr \_ webext.contoso.com \_ LoadBalance \_ SSL**.</span><span class="sxs-lookup"><span data-stu-id="99bad-237">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="99bad-238">Double-cliquez sur la règle pour ouvrir la boîte de dialogue **modifier la règle de trafic entrant** .</span><span class="sxs-lookup"><span data-stu-id="99bad-238">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="99bad-239">Cliquez sur **Ajouter...**</span><span class="sxs-lookup"><span data-stu-id="99bad-239">Click **Add…**</span></span> <span data-ttu-id="99bad-240">dans la boîte de dialogue **conditions** .</span><span class="sxs-lookup"><span data-stu-id="99bad-240">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="99bad-241">Dans la **condition Add** de l' **entrée de condition :** type **{http \_ Host}**.</span><span class="sxs-lookup"><span data-stu-id="99bad-241">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="99bad-242">(En fur et à mesure que vous tapez, une boîte de dialogue s’affiche pour vous permettre de sélectionner la condition).</span><span class="sxs-lookup"><span data-stu-id="99bad-242">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="99bad-243">sous **Vérifier la chaîne d’entrée :** sélectionnez **correspond au modèle**.</span><span class="sxs-lookup"><span data-stu-id="99bad-243">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="99bad-244">Dans le type **d’entrée pattern** **\*** .</span><span class="sxs-lookup"><span data-stu-id="99bad-244">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="99bad-245">**Ignorer la casse** doit être sélectionné.</span><span class="sxs-lookup"><span data-stu-id="99bad-245">**Ignore case** should be selected.</span></span> <span data-ttu-id="99bad-246">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="99bad-246">Click **OK**.</span></span>
    
      - <span data-ttu-id="99bad-247">Faites défiler la boîte de dialogue **modifier la règle de trafic entrant** pour localiser la boîte de dialogue **action** .</span><span class="sxs-lookup"><span data-stu-id="99bad-247">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="99bad-248">**Type d’action :** doit être défini sur **acheminer vers la batterie de serveurs**, **modèle :** défini sur **https://**, **batterie de serveurs :** définit sur l’URL à laquelle cette règle s’applique.</span><span class="sxs-lookup"><span data-stu-id="99bad-248">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="99bad-249">Pour cet exemple, il doit être défini sur **webext.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="99bad-249">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="99bad-250">**Path :** est défini sur **/{R : 0}**</span><span class="sxs-lookup"><span data-stu-id="99bad-250">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="99bad-251">Cliquez sur **appliquer** pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="99bad-251">Click **Apply** to save your changes.</span></span> <span data-ttu-id="99bad-252">Cliquez sur **retour aux règles** pour revenir aux règles de réécriture d’URL.</span><span class="sxs-lookup"><span data-stu-id="99bad-252">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="99bad-253">Répétez la procédure définie à l’étape 14 pour chacune des règles de réécriture SSL que vous avez définies, une par URL de batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="99bad-253">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="99bad-254">Par défaut, les règles HTTP sont également créées et sont représentées par des noms similaires aux règles SSL.</span><span class="sxs-lookup"><span data-stu-id="99bad-254">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="99bad-255">Pour notre exemple actuel, la règle HTTP est nommée <STRONG>ARR_webext. contoso. com _loadbalance</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="99bad-255">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="99bad-256">Aucune modification n’est requise pour ces règles et elles peuvent être ignorées en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="99bad-256">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="99bad-257">Pour modifier les propriétés de la règle de publication Web dans TMG 2010</span><span class="sxs-lookup"><span data-stu-id="99bad-257">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="99bad-258">Cliquez sur **Démarrer**, pointez sur **programmes**, sélectionnez **Microsoft Forefront TMG**, puis cliquez sur **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="99bad-258">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="99bad-259">Dans le volet de gauche, développez **NomServeur**, puis cliquez sur **Stratégie de pare-feu**.</span><span class="sxs-lookup"><span data-stu-id="99bad-259">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="99bad-260">Dans le volet des détails, cliquez avec le bouton droit sur la règle de publication de serveur web que vous avez créée précédemment (par exemple, LyncServerExternalRule), puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="99bad-260">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="99bad-261">Dans la page **Propriétés**, sous l’onglet **De**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="99bad-261">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="99bad-262">Dans la liste **Cette règle s’applique au trafic émanant de ces sources**, cliquez sur **Partout**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="99bad-262">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="99bad-263">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="99bad-263">Click **Add**.</span></span>
    
      - <span data-ttu-id="99bad-264">Dans la boîte de dialogue **Ajouter des entités réseau**, développez **Réseaux**, cliquez sur **Externe**, puis sur **Ajouter**, puis sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="99bad-264">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="99bad-265">Sous l’onglet **À**, vérifiez que la case à cocher **Transmettre l’en-tête de l’hôte d’origine plutôt que l’en-tête réel** est activée.</span><span class="sxs-lookup"><span data-stu-id="99bad-265">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="99bad-266">Dans la zone **Pontage**, activez la case à cocher **Rediriger la demande vers le port SSL**, puis spécifiez le port **4443**.</span><span class="sxs-lookup"><span data-stu-id="99bad-266">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="99bad-267">Sous l’onglet **Nom public**, ajoutez les URL simples (par exemple, meet.contoso.com et dialin.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="99bad-267">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="99bad-268">Cliquez sur **Appliquer** pour enregistrer les modifications, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="99bad-268">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="99bad-269">Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.</span><span class="sxs-lookup"><span data-stu-id="99bad-269">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="99bad-270">Pour modifier les propriétés de la règle de publication Web dans IIS ARR</span><span class="sxs-lookup"><span data-stu-id="99bad-270">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="99bad-271">Cliquez sur **Démarrer**, sélectionnez **programmes**, **Outils d’administration**, puis **Gestionnaire des services Internet (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="99bad-271">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="99bad-272">Sur le côté gauche de la console, cliquez sur le nom du serveur IIS.</span><span class="sxs-lookup"><span data-stu-id="99bad-272">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="99bad-273">Au milieu de la console, recherchez **URL Rewrite** sous **IIS**.</span><span class="sxs-lookup"><span data-stu-id="99bad-273">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="99bad-274">Double-cliquez sur réécriture d’URL pour ouvrir la configuration des règles de réécriture d’URL.</span><span class="sxs-lookup"><span data-stu-id="99bad-274">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="99bad-275">Double-cliquez sur la règle à modifier.</span><span class="sxs-lookup"><span data-stu-id="99bad-275">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="99bad-276">Effectuez vos modifications, selon vos besoins, dans l' **URL de correspondance**, les **conditions**, les **variables de serveur** ou l' **action**.</span><span class="sxs-lookup"><span data-stu-id="99bad-276">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="99bad-277">Cliquez sur **appliquer** pour valider vos modifications.</span><span class="sxs-lookup"><span data-stu-id="99bad-277">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="99bad-278">Cliquez sur **retour aux règles** pour modifier d’autres règles ou fermez la console du **Gestionnaire IIS** si vous avez effectué vos modifications.</span><span class="sxs-lookup"><span data-stu-id="99bad-278">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

