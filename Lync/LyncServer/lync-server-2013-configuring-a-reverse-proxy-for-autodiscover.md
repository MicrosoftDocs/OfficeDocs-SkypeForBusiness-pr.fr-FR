---
title: 'Lync Server 2013 : configuration d’un proxy inverse pour la découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 568e96b999a74ec621f8c7386f24e83d3848721c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="808d5-102">Configuration d’un proxy inverse pour la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="808d5-102">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="808d5-103">_**Dernière modification de la rubrique :** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="808d5-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="808d5-104">Découverte automatique et prise en charge des clients à l’aide de la découverte automatique nécessite la modification d’une règle de publication Web existante ou la création d’une nouvelle règle de publication Web pour le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="808d5-104">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="808d5-105">La modification ou la création d’une nouvelle règle de publication n’est pas tributaire de la décision de mettre à jour ou de ne pas mettre à jour les listes d’autres noms de sujet sur les certificats de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="808d5-105">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="808d5-106">Si vous décidez d’utiliser le protocole HTTPs pour les demandes de service de découverte automatique Lync Server 2013 initiales et mettez à jour les listes des autres noms de sujet sur les certificats de proxy inverse, vous devez affecter le certificat public mis à jour à l’écouteur SSL (Secure Sockets Layer) sur votre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="808d5-106">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="808d5-107">La mise à jour requise du certificat externe (public) inclut l’entrée de l’autre nom de l’objet (SAN) pour lyncdiscover. \<nom\>de domaine.</span><span class="sxs-lookup"><span data-stu-id="808d5-107">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="808d5-108">Vous devez ensuite modifier l’écouteur existant pour les services Web externes ou créer une nouvelle règle de publication Web pour l’URL du service de découverte automatique externe, par exemple **lyncdiscover.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="808d5-108">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="808d5-109">Si vous n’avez pas encore de règle de publication Web pour l’URL de services Web Lync Server 2013 externe pour votre pool frontal et votre pool directeur (si vous avez déployé des directeurs), vous devez également publier une règle pour cela.</span><span class="sxs-lookup"><span data-stu-id="808d5-109">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="808d5-110">La règle de publication et l’écouteur du proxy inverse peuvent être utilisés par les services web externes et le service de découverte automatique, à condition que le certificat assigné à l’écouteur contienne le nom de sujet et les autres noms de sujet nécessaires aux deux.</span><span class="sxs-lookup"><span data-stu-id="808d5-110">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="808d5-111">Pour plus d’informations sur la configuration par défaut du port d’écoute Web et de la règle de publication, voir <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up Reverse Proxy Servers for Lync Server 2013</A> pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="808d5-111">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="808d5-112">Si vous décidez d’utiliser HTTP pour les demandes initiales du service de découverte automatique pour ne pas avoir à mettre à jour les autres noms de sujet pour le proxy inverse, vous devez créer ou modifier une règle de publication web pour le port 80.</span><span class="sxs-lookup"><span data-stu-id="808d5-112">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="808d5-113">Les procédures de cette section indiquent comment créer ou modifier les règles de publication web dans Microsoft Forefront Threat Management Gateway 2010 pour la découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="808d5-113">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="808d5-p104">Ces procédures supposent que vous avez installé la version Standard Edition de Forefront Threat Management Gateway (TMG) 2010. Si vous utilisez un autre proxy inverse, les procédures, bien qu’identiques, devront être adaptées en tenant compte de la documentation du produit tiers.</span><span class="sxs-lookup"><span data-stu-id="808d5-p104">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="808d5-116">Pour créer une règle de publication web pour l’URL de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="808d5-116">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="808d5-117">Cliquez sur **Démarrer**, pointez sur **Programmes**, pointez sur **Microsoft Forefront TMG**, puis cliquez sur **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="808d5-117">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="808d5-118">Dans le volet de gauche, développez **NomServeur**, cliquez avec le bouton droit sur **Stratégie de pare-feu**, pointez sur **Nouveau**, puis cliquez sur **Règle de publication web**.</span><span class="sxs-lookup"><span data-stu-id="808d5-118">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="808d5-119">Dans la page **Assistant Nouvelle règle de publication web**, entrez un nom convivial pour la nouvelle règle de publication (par exemple, LyncDiscoveryURL).</span><span class="sxs-lookup"><span data-stu-id="808d5-119">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="808d5-120">Dans la page **Sélectionner l’action de la règle**, sélectionnez **Autoriser**.</span><span class="sxs-lookup"><span data-stu-id="808d5-120">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="808d5-121">Dans la page **Type de publication**, sélectionnez **Publier un seul site web ou équilibreur de charge**.</span><span class="sxs-lookup"><span data-stu-id="808d5-121">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="808d5-122">Dans la page **Sécurité de connexion serveur**, sélectionnez **Utiliser SSL pour se connecter au serveur web publié ou à la batterie de serveurs**.</span><span class="sxs-lookup"><span data-stu-id="808d5-122">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="808d5-123">Sur la page **Détails de publication interne** , dans **nom de site interne**, tapez le nom de domaine complet (FQDN) de votre pool de directeurs (par exemple, lyncdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="808d5-123">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="808d5-124">Si vous créez une règle pour l’URL des services Web externes sur le pool frontal, tapez le nom de domaine complet du pool frontal (par exemple, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="808d5-124">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="808d5-125">Sur la page **Détails de publication interne** , dans **chemin (facultatif)**, \*\* / \*\* tapez comme chemin d’accès du dossier à publier, puis sélectionnez **transférer l’en-tête d’hôte d’origine**.</span><span class="sxs-lookup"><span data-stu-id="808d5-125">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="808d5-126">Dans la page **Informations sur les noms publics**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="808d5-126">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="808d5-127">Sous **Accepter les demandes pour**, sélectionnez **Ce nom de domaine**.</span><span class="sxs-lookup"><span data-stu-id="808d5-127">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="808d5-128">Dans **nom public**, tapez **lyncdiscover.** \<SIPDOMAIN\> (URL du service de découverte automatique externe).</span><span class="sxs-lookup"><span data-stu-id="808d5-128">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="808d5-129">Si vous créez une règle pour l’URL des services Web externes sur le pool frontal, tapez le nom de domaine complet (FQDN) des services Web externes sur votre pool frontal (par exemple, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="808d5-129">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="808d5-130">Dans **chemin d’accès**, tapez \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="808d5-130">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="808d5-131">Dans la page **Sélectionner le port d’écoute**, dans **Port d’écoute web**, sélectionnez votre écouteur SSL existant avec le certificat public mis à jour.</span><span class="sxs-lookup"><span data-stu-id="808d5-131">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="808d5-132">Dans la page **Délégation de l’authentification**, sélectionnez **Aucune délégation, mais le client peut authentifier directement**.</span><span class="sxs-lookup"><span data-stu-id="808d5-132">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="808d5-133">Dans la page **Ensemble d’utilisateurs**, cliquez sur **Tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="808d5-133">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="808d5-134">Dans la page **Fin de l’Assistant Nouvelle règle de publication web**, vérifiez que les paramètres de la règle de publication web sont corrects, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="808d5-134">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="808d5-135">Dans la liste Forefront TMG de règles de publication web, double-cliquez sur la nouvelle règle que vous venez d’ajouter pour ouvrir les **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="808d5-135">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="808d5-136">Sous l’onglet **À**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="808d5-136">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="808d5-137">Sélectionnez **Transmettre l’en-tête de l’hôte d’origine plutôt que l’en-tête réel**.</span><span class="sxs-lookup"><span data-stu-id="808d5-137">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="808d5-138">Sélectionnez **Les demandes semblent émaner de l’ordinateur Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="808d5-138">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="808d5-139">Sous l’onglet **Pontage**, configurez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="808d5-139">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="808d5-140">Sélectionnez **Serveur web**.</span><span class="sxs-lookup"><span data-stu-id="808d5-140">Select **Web server**.</span></span>
    
      - <span data-ttu-id="808d5-141">Sélectionnez **Rediriger les demandes au port HTTP** et tapez **8080** comme numéro de port.</span><span class="sxs-lookup"><span data-stu-id="808d5-141">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="808d5-142">Sélectionnez **Rediriger les demandes au port SSL** et tapez **4443** comme numéro de port.</span><span class="sxs-lookup"><span data-stu-id="808d5-142">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="808d5-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="808d5-143">Click **OK**.</span></span>

18. <span data-ttu-id="808d5-144">Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.</span><span class="sxs-lookup"><span data-stu-id="808d5-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="808d5-145">Cliquez sur **Tester la règle** pour vérifier que votre nouvelle règle est configurée correctement.</span><span class="sxs-lookup"><span data-stu-id="808d5-145">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="808d5-146">Pour modifier une règle de publication web existante afin d’ajouter l’autre nom de sujet et l’URL du service de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="808d5-146">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="808d5-147">Cliquez sur **Démarrer**, pointez sur **Programmes**, pointez sur **Microsoft Forefront TMG**, puis cliquez sur **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="808d5-147">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="808d5-148">Vous devrez répéter la modification pour chaque règle de publication et chaque écouteur que vous possédez.</span><span class="sxs-lookup"><span data-stu-id="808d5-148">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="808d5-149">En règle générale, il s’agit d’une règle et d’un écouteur pour les pools frontaux et un pour les directeurs ou pools directeurs facultatifs, si vous les avez déployés.</span><span class="sxs-lookup"><span data-stu-id="808d5-149">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="808d5-p108">Dans le volet gauche, développez **NomServeur**, cliquez avec le bouton droit sur **Stratégie de pare-feu**, puis cliquez sur la règle applicable. Sous l’onglet **Tâches**, cliquez sur **Modifier la règle sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="808d5-p108">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="808d5-152">Sous l’onglet **Nom public**, dans **Cette règle s’applique à**, sélectionnez **Demandes pour les sites web suivants**.</span><span class="sxs-lookup"><span data-stu-id="808d5-152">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="808d5-153">Cliquez sur **Ajouter**, tapez le nom du nouveau site de découverte automatique (par exemple, « lyncdiscover.contoso.com »), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="808d5-153">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="808d5-p109">Sous l’onglet **Écouteur**, cliquez sur **Sélectionner un certificat** et assignez le nouveau certificat avec les entrées d’autres noms de sujet ajoutées du service de découverte automatique. Fermez les propriétés d’écouteur et de publication web.</span><span class="sxs-lookup"><span data-stu-id="808d5-p109">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="808d5-156">Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.</span><span class="sxs-lookup"><span data-stu-id="808d5-156">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="808d5-157">Cliquez sur **Tester la règle** pour vérifier que votre nouvelle règle est configurée correctement.</span><span class="sxs-lookup"><span data-stu-id="808d5-157">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="808d5-158">Pour créer une règle de publication web pour le port 80</span><span class="sxs-lookup"><span data-stu-id="808d5-158">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="808d5-159">Cliquez sur **Démarrer**, pointez sur **Programmes**, pointez sur **Microsoft Forefront TMG**, puis cliquez sur **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="808d5-159">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="808d5-160">Dans le volet de gauche, développez **NomServeur**, cliquez avec le bouton droit sur **Stratégie de pare-feu**, pointez sur **Nouveau**, puis cliquez sur **Règle de publication web**.</span><span class="sxs-lookup"><span data-stu-id="808d5-160">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="808d5-161">Dans la page **Assistant Nouvelle règle de publication web**, entrez un nom convivial pour la nouvelle règle de publication (par exemple, Lync Autodiscover (HTTP)).</span><span class="sxs-lookup"><span data-stu-id="808d5-161">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="808d5-162">Dans la page **Sélectionner l’action de la règle**, sélectionnez **Autoriser**.</span><span class="sxs-lookup"><span data-stu-id="808d5-162">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="808d5-163">Dans la page **Type de publication**, sélectionnez **Publier un seul site web ou équilibreur de charge**.</span><span class="sxs-lookup"><span data-stu-id="808d5-163">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="808d5-164">Dans la page **Sécurité de connexion serveur**, sélectionnez **Utiliser des connexions non sécurisées pour se connecter au serveur web publié ou à la batterie de serveurs**.</span><span class="sxs-lookup"><span data-stu-id="808d5-164">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="808d5-165">Sur la page **Détails de publication interne** , dans **nom de site interne**, tapez le nom de domaine complet des services Web internes pour votre pool frontal (par exemple, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="808d5-165">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="808d5-166">Sur la page **Détails de publication interne** , dans **chemin d’accès (facultatif)**, tapez \*\* / \*\* comme chemin d’accès du dossier à publier, puis sélectionnez **transférer l’en-tête d’hôte d’origine au lieu de celui spécifié dans le champ nom de site interne**.</span><span class="sxs-lookup"><span data-stu-id="808d5-166">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="808d5-167">Dans la page **Informations sur les noms publics**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="808d5-167">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="808d5-168">Sous **Accepter les demandes pour**, sélectionnez **Ce nom de domaine**.</span><span class="sxs-lookup"><span data-stu-id="808d5-168">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="808d5-169">Dans **nom public**, tapez **lyncdiscover.** \<SIPDOMAIN\> (URL du service de découverte automatique externe).</span><span class="sxs-lookup"><span data-stu-id="808d5-169">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="808d5-170">Dans **chemin d’accès**, tapez \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="808d5-170">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="808d5-171">Dans la page **Sélectionner un port d’écoute**, dans **Port d’écoute web**, sélectionnez un écouteur web ou utilisez l’Assistant Nouvelle définition d’écouteur web pour en créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="808d5-171">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="808d5-172">Dans la page **Délégation de l’authentification**, sélectionnez **Aucune délégation, et le client ne peut pas authentifier directement**.</span><span class="sxs-lookup"><span data-stu-id="808d5-172">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="808d5-173">Dans la page **Ensemble d’utilisateurs**, cliquez sur **Tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="808d5-173">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="808d5-174">Dans la page **Fin de l’Assistant Nouvelle règle de publication web**, vérifiez que les paramètres de la règle de publication web sont corrects, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="808d5-174">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="808d5-175">Dans la liste Forefront TMG de règles de publication web, double-cliquez sur la nouvelle règle que vous venez d’ajouter pour ouvrir les **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="808d5-175">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="808d5-176">Sous l’onglet **Pontage**, configurez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="808d5-176">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="808d5-177">Sélectionnez **Serveur web**.</span><span class="sxs-lookup"><span data-stu-id="808d5-177">Select **Web server**.</span></span>
    
      - <span data-ttu-id="808d5-178">Sélectionnez **Rediriger les demandes au port HTTP** et tapez **8080** comme numéro de port.</span><span class="sxs-lookup"><span data-stu-id="808d5-178">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="808d5-179">Vérifiez que l’option **Rediriger les demandes au port SSL** n’est pas sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="808d5-179">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="808d5-180">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="808d5-180">Click **OK**.</span></span>

17. <span data-ttu-id="808d5-181">Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.</span><span class="sxs-lookup"><span data-stu-id="808d5-181">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="808d5-182">Cliquez sur **Tester la règle** pour vérifier que votre nouvelle règle est configurée correctement.</span><span class="sxs-lookup"><span data-stu-id="808d5-182">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="808d5-183">Vérifiez que l’URL du service de découverte automatique externe n’est définie sur aucune autre règle de publication web.</span><span class="sxs-lookup"><span data-stu-id="808d5-183">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="808d5-184">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="808d5-184">See Also</span></span>


[<span data-ttu-id="808d5-185">Configuration des serveurs proxy inverses pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="808d5-185">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

