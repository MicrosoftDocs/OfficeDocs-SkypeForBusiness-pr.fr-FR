---
title: 'Lync Server 2013 : configuration d’un proxy inverse pour la découverte automatique'
description: 'Lync Server 2013 : configuration d’un proxy inverse pour la découverte automatique.'
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
ms.openlocfilehash: 1f7873df063c526b4e51678ded02ca11d27c5e01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553950"
---
# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="d6f8b-103">Configuration d’un proxy inverse pour la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6f8b-103">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6f8b-104">_**Dernière modification de la rubrique :** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="d6f8b-104">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="d6f8b-105">Découverte automatique et prise en charge des clients à l’aide de la découverte automatique nécessite la modification d’une règle de publication Web existante ou la création d’une nouvelle règle de publication Web pour le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-105">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="d6f8b-106">La modification ou la création d’une nouvelle règle de publication n’est pas tributaire de la décision de mettre à jour ou de ne pas mettre à jour les listes d’autres noms de sujet sur les certificats de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-106">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="d6f8b-107">Si vous décidez d’utiliser le protocole HTTPs pour les demandes de service de découverte automatique Lync Server 2013 initiales et de mettre à jour les listes des autres noms du sujet sur les certificats de proxy inverse, vous devez affecter le certificat public mis à jour à l’écouteur SSL (Secure Sockets Layer) de votre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-107">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="d6f8b-108">La mise à jour requise du certificat externe (public) inclut l’entrée de l’autre nom de sujet (SAN) pour lyncdiscover. \<domain name\> .</span><span class="sxs-lookup"><span data-stu-id="d6f8b-108">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="d6f8b-109">Vous devez ensuite modifier l’écouteur existant pour les services Web externes ou créer une nouvelle règle de publication Web pour l’URL du service de découverte automatique externe, par exemple **lyncdiscover.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-109">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="d6f8b-110">Si vous n’avez pas encore de règle de publication Web pour l’URL de services Web Lync Server 2013 externe pour votre pool frontal et votre pool directeur (si vous avez déployé des directeurs), vous devez également publier une règle pour cela.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-110">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6f8b-111">La règle de publication et l’écouteur du proxy inverse peuvent être utilisés par les services web externes et le service de découverte automatique, à condition que le certificat assigné à l’écouteur contienne le nom de sujet et les autres noms de sujet nécessaires aux deux.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-111">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="d6f8b-112">Pour plus d’informations sur la configuration par défaut du port d’écoute Web et de la règle de publication, voir <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up Reverse Proxy Servers for Lync Server 2013</A> pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-112">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="d6f8b-113">Si vous décidez d’utiliser HTTP pour les demandes initiales du service de découverte automatique pour ne pas avoir à mettre à jour les autres noms de sujet pour le proxy inverse, vous devez créer ou modifier une règle de publication web pour le port 80.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-113">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="d6f8b-114">Les procédures de cette section indiquent comment créer ou modifier les règles de publication web dans Microsoft Forefront Threat Management Gateway 2010 pour la découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-114">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6f8b-p104">Ces procédures supposent que vous avez installé la version Standard Edition de Forefront Threat Management Gateway (TMG) 2010. Si vous utilisez un autre proxy inverse, les procédures, bien qu’identiques, devront être adaptées en tenant compte de la documentation du produit tiers.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-p104">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="d6f8b-117">Pour créer une règle de publication web pour l’URL de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="d6f8b-117">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="d6f8b-118">Cliquez sur **Démarrer**, pointez sur **Programmes**, pointez sur **Microsoft Forefront TMG**, puis cliquez sur **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-118">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="d6f8b-119">Dans le volet de gauche, développez **NomServeur**, cliquez avec le bouton droit sur **Stratégie de pare-feu**, pointez sur **Nouveau**, puis cliquez sur **Règle de publication web**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-119">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="d6f8b-120">Dans la page **Assistant Nouvelle règle de publication web**, entrez un nom convivial pour la nouvelle règle de publication (par exemple, LyncDiscoveryURL).</span><span class="sxs-lookup"><span data-stu-id="d6f8b-120">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="d6f8b-121">Dans la page **Sélectionner l’action de la règle**, sélectionnez **Autoriser**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-121">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="d6f8b-122">Dans la page **Type de publication**, sélectionnez **Publier un seul site web ou équilibreur de charge**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-122">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="d6f8b-123">Dans la page **Sécurité de connexion serveur**, sélectionnez **Utiliser SSL pour se connecter au serveur web publié ou à la batterie de serveurs**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-123">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="d6f8b-124">Sur la page **Détails de publication interne** , dans **nom de site interne**, tapez le nom de domaine complet (FQDN) de votre pool de directeurs (par exemple, lyncdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="d6f8b-124">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="d6f8b-125">Si vous créez une règle pour l’URL des services Web externes sur le pool frontal, tapez le nom de domaine complet du pool frontal (par exemple, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="d6f8b-125">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="d6f8b-126">Sur la page **Détails de publication interne** , dans **chemin (facultatif)**, tapez **/\*** comme chemin d’accès du dossier à publier, puis sélectionnez **transférer l’en-tête d’hôte d’origine**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-126">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="d6f8b-127">Dans la page **Informations sur les noms publics**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d6f8b-127">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="d6f8b-128">Sous **Accepter les demandes pour**, sélectionnez **Ce nom de domaine**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-128">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="d6f8b-129">Dans **nom public**, tapez **lyncdiscover.**\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="d6f8b-129">In **Public Name**, type **lyncdiscover.**\<sipdomain\></span></span> <span data-ttu-id="d6f8b-130">(URL du service de découverte automatique externe).</span><span class="sxs-lookup"><span data-stu-id="d6f8b-130">(the external Autodiscover Service URL).</span></span> <span data-ttu-id="d6f8b-131">Si vous créez une règle pour l’URL des services Web externes sur le pool frontal, tapez le nom de domaine complet (FQDN) des services Web externes sur votre pool frontal (par exemple, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d6f8b-131">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="d6f8b-132">Dans **chemin d’accès**, tapez **/\*** .</span><span class="sxs-lookup"><span data-stu-id="d6f8b-132">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="d6f8b-133">Dans la page **Sélectionner le port d’écoute**, dans **Port d’écoute web**, sélectionnez votre écouteur SSL existant avec le certificat public mis à jour.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-133">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="d6f8b-134">Dans la page **Délégation de l’authentification**, sélectionnez **Aucune délégation, mais le client peut authentifier directement**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="d6f8b-135">Dans la page **Ensemble d’utilisateurs**, cliquez sur **Tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-135">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="d6f8b-136">Dans la page **Fin de l’Assistant Nouvelle règle de publication web**, vérifiez que les paramètres de la règle de publication web sont corrects, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-136">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="d6f8b-137">Dans la liste Forefront TMG de règles de publication web, double-cliquez sur la nouvelle règle que vous venez d’ajouter pour ouvrir les **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-137">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="d6f8b-138">Sous l’onglet **À**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d6f8b-138">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="d6f8b-139">Sélectionnez **Transmettre l’en-tête de l’hôte d’origine plutôt que l’en-tête réel**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-139">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="d6f8b-140">Sélectionnez **Les demandes semblent émaner de l’ordinateur Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-140">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="d6f8b-141">Sous l’onglet **Pontage**, configurez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d6f8b-141">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="d6f8b-142">Sélectionnez **Serveur web**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-142">Select **Web server**.</span></span>
    
      - <span data-ttu-id="d6f8b-143">Sélectionnez **Rediriger les demandes au port HTTP** et tapez **8080** comme numéro de port.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-143">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="d6f8b-144">Sélectionnez **Rediriger les demandes au port SSL** et tapez **4443** comme numéro de port.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-144">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="d6f8b-145">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-145">Click **OK**.</span></span>

18. <span data-ttu-id="d6f8b-146">Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-146">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="d6f8b-147">Cliquez sur **Tester la règle** pour vérifier que votre nouvelle règle est configurée correctement.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-147">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="d6f8b-148">Pour modifier une règle de publication web existante afin d’ajouter l’autre nom de sujet et l’URL du service de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="d6f8b-148">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="d6f8b-149">Cliquez sur **Démarrer**, pointez sur **Programmes**, pointez sur **Microsoft Forefront TMG**, puis cliquez sur **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-149">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d6f8b-150">Vous devrez répéter la modification pour chaque règle de publication et chaque écouteur que vous possédez.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-150">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="d6f8b-151">En règle générale, il s’agit d’une règle et d’un écouteur pour les pools frontaux et un pour les directeurs ou pools directeurs facultatifs, si vous les avez déployés.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-151">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="d6f8b-p108">Dans le volet gauche, développez **NomServeur**, cliquez avec le bouton droit sur **Stratégie de pare-feu**, puis cliquez sur la règle applicable. Sous l’onglet **Tâches**, cliquez sur **Modifier la règle sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-p108">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="d6f8b-154">Sous l’onglet **Nom public**, dans **Cette règle s’applique à**, sélectionnez **Demandes pour les sites web suivants**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-154">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="d6f8b-155">Cliquez sur **Ajouter**, tapez le nom du nouveau site de découverte automatique (par exemple, « lyncdiscover.contoso.com »), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-155">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="d6f8b-p109">Sous l’onglet **Écouteur**, cliquez sur **Sélectionner un certificat** et assignez le nouveau certificat avec les entrées d’autres noms de sujet ajoutées du service de découverte automatique. Fermez les propriétés d’écouteur et de publication web.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-p109">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="d6f8b-158">Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-158">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="d6f8b-159">Cliquez sur **Tester la règle** pour vérifier que votre nouvelle règle est configurée correctement.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-159">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="d6f8b-160">Pour créer une règle de publication web pour le port 80</span><span class="sxs-lookup"><span data-stu-id="d6f8b-160">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="d6f8b-161">Cliquez sur **Démarrer**, pointez sur **Programmes**, pointez sur **Microsoft Forefront TMG**, puis cliquez sur **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-161">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="d6f8b-162">Dans le volet de gauche, développez **NomServeur**, cliquez avec le bouton droit sur **Stratégie de pare-feu**, pointez sur **Nouveau**, puis cliquez sur **Règle de publication web**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-162">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="d6f8b-163">Dans la page **Assistant Nouvelle règle de publication web**, entrez un nom convivial pour la nouvelle règle de publication (par exemple, Lync Autodiscover (HTTP)).</span><span class="sxs-lookup"><span data-stu-id="d6f8b-163">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="d6f8b-164">Dans la page **Sélectionner l’action de la règle**, sélectionnez **Autoriser**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-164">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="d6f8b-165">Dans la page **Type de publication**, sélectionnez **Publier un seul site web ou équilibreur de charge**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-165">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="d6f8b-166">Dans la page **Sécurité de connexion serveur**, sélectionnez **Utiliser des connexions non sécurisées pour se connecter au serveur web publié ou à la batterie de serveurs**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-166">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="d6f8b-167">Sur la page **Détails de publication interne** , dans **nom de site interne**, tapez le nom de domaine complet des services Web internes pour votre pool frontal (par exemple, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="d6f8b-167">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="d6f8b-168">Sur la page **Détails de publication interne** , dans **chemin d’accès (facultatif)**, tapez **/\*** comme chemin d’accès du dossier à publier, puis sélectionnez **transférer l’en-tête d’hôte d’origine au lieu de celui spécifié dans le champ nom de site interne**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-168">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="d6f8b-169">Dans la page **Informations sur les noms publics**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d6f8b-169">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="d6f8b-170">Sous **Accepter les demandes pour**, sélectionnez **Ce nom de domaine**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-170">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="d6f8b-171">Dans **nom public**, tapez **lyncdiscover.**\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="d6f8b-171">In **Public Name**, type **lyncdiscover.**\<sipdomain\></span></span> <span data-ttu-id="d6f8b-172">(URL du service de découverte automatique externe).</span><span class="sxs-lookup"><span data-stu-id="d6f8b-172">(the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="d6f8b-173">Dans **chemin d’accès**, tapez **/\*** .</span><span class="sxs-lookup"><span data-stu-id="d6f8b-173">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="d6f8b-174">Dans la page **Sélectionner un port d’écoute**, dans **Port d’écoute web**, sélectionnez un écouteur web ou utilisez l’Assistant Nouvelle définition d’écouteur web pour en créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-174">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="d6f8b-175">Dans la page **Délégation de l’authentification**, sélectionnez **Aucune délégation, et le client ne peut pas authentifier directement**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-175">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="d6f8b-176">Dans la page **Ensemble d’utilisateurs**, cliquez sur **Tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-176">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="d6f8b-177">Dans la page **Fin de l’Assistant Nouvelle règle de publication web**, vérifiez que les paramètres de la règle de publication web sont corrects, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-177">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="d6f8b-178">Dans la liste Forefront TMG de règles de publication web, double-cliquez sur la nouvelle règle que vous venez d’ajouter pour ouvrir les **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-178">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="d6f8b-179">Sous l’onglet **Pontage**, configurez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d6f8b-179">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="d6f8b-180">Sélectionnez **Serveur web**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-180">Select **Web server**.</span></span>
    
      - <span data-ttu-id="d6f8b-181">Sélectionnez **Rediriger les demandes au port HTTP** et tapez **8080** comme numéro de port.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-181">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="d6f8b-182">Vérifiez que l’option **Rediriger les demandes au port SSL** n’est pas sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-182">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="d6f8b-183">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-183">Click **OK**.</span></span>

17. <span data-ttu-id="d6f8b-184">Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-184">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="d6f8b-185">Cliquez sur **Tester la règle** pour vérifier que votre nouvelle règle est configurée correctement.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-185">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="d6f8b-186">Vérifiez que l’URL du service de découverte automatique externe n’est définie sur aucune autre règle de publication web.</span><span class="sxs-lookup"><span data-stu-id="d6f8b-186">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6f8b-187">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d6f8b-187">See Also</span></span>


[<span data-ttu-id="d6f8b-188">Configuration des serveurs proxy inverses pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6f8b-188">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

