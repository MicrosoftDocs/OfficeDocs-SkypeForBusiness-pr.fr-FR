---
title: 'Lync Server 2013 : Configuration du proxy inverse pour la mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657ddf0711b0a14c9ce861a0f237977c9a2369c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a><span data-ttu-id="07aa1-102">Configuration du proxy inverse pour la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07aa1-102">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07aa1-103">_**Dernière modification de la rubrique:** 2014-03-20_</span><span class="sxs-lookup"><span data-stu-id="07aa1-103">_**Topic Last Modified:** 2014-03-20_</span></span>

<span data-ttu-id="07aa1-104">Si vous souhaitez utiliser la découverte automatique pour les clients d’appareils mobiles, vous devez modifier ou créer une nouvelle règle de publication Web pour le proxy inverse, que vous ayez ou non mis à jour les listes de noms de remplacement de l’objet sur les certificats proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="07aa1-104">If you want to use automatic discovery for mobile device clients, you need to modify an existing or create a new web publishing rule for the reverse proxy whether or not you update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="07aa1-105">Si vous décidez d’utiliser HTTPs pour les demandes de service de découverte automatique Lync Server 2013 et de mettre à jour les listes de noms de remplacement d’objet sur les certificats de proxy inverse, vous devez affecter le certificat public mis à jour à l’écouteur SSL (Secure Sockets Layer) sur votre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="07aa1-105">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="07aa1-106">Pour plus d’informations sur les entrées de nom de remplacement d’objet requises, voir [configuration technique requise pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="07aa1-106">For details about the required subject alternative name entries, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="07aa1-107">Vous devez ensuite modifier l’écouteur existant pour les services Web externes ou créer une nouvelle règle de publication Web pour l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="07aa1-107">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="07aa1-108">Si vous ne disposez pas encore d’une règle de publication sur le Web pour l’URL des services Web Lync Server 2013 externes pour votre pool frontal, vous devez également publier une règle pour celle-ci.</span><span class="sxs-lookup"><span data-stu-id="07aa1-108">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool, you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07aa1-109">La règle de publication de proxy inverse et l’écouteur peuvent service à la fois les services Web externes et le service de découverte automatique, tant que le certificat attribué à l’écouteur contient le nom du sujet et les noms de remplacement de l’objet requis pour les deux.</span><span class="sxs-lookup"><span data-stu-id="07aa1-109">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="07aa1-110">Pour plus d’informations sur la configuration par défaut de l’écouteur et de la règle de publication sur le Web, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configuration de serveurs proxy inverse pour Lync Server 2013</A> pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="07aa1-110">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="07aa1-111">Si vous décidez d’utiliser HTTP pour les demandes de service de découverte automatique initiales afin de ne pas avoir besoin de mettre à jour les autres noms d’objet du proxy inverse, vous devez créer ou modifier une règle de publication Web pour le port 80.</span><span class="sxs-lookup"><span data-stu-id="07aa1-111">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="07aa1-112">Les procédures décrites dans cette section expliquent comment créer ou modifier les règles de publication Web dans Microsoft Forefront Threat Management Gateway 2010 pour la découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="07aa1-112">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07aa1-113">Les procédures suivantes présupposent que vous avez installé l’édition standard de Forefront Threat Management Gateway (TMG) 2010.</span><span class="sxs-lookup"><span data-stu-id="07aa1-113">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010.</span></span> <span data-ttu-id="07aa1-114">Si vous utilisez un autre proxy inverse, les procédures sont similaires, mais doivent être mappées à la documentation du produit tiers.</span><span class="sxs-lookup"><span data-stu-id="07aa1-114">If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="07aa1-115">Pour créer une règle de publication Web pour l’URL de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="07aa1-115">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="07aa1-116">Cliquez sur **Démarrer**, pointez sur **programmes**, sur **Microsoft Forefront TMG**, puis cliquez sur gestion de **Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-116">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="07aa1-117">Dans le volet gauche, développez **NomServeur**, cliquez avec le bouton droit sur **stratégie de pare-feu**, pointez sur **nouveau**, puis cliquez sur règle de **publication de site Web**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-117">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="07aa1-118">Dans la page **Bienvenue dans la nouvelle règle de publication Web** , tapez un nom d’affichage pour la nouvelle règle de publication (par exemple, LyncDiscoveryURL).</span><span class="sxs-lookup"><span data-stu-id="07aa1-118">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="07aa1-119">Dans la page **Sélectionner une action de règle** , sélectionnez **autoriser**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-119">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="07aa1-120">Dans la page **type de publication** , sélectionnez **publier un site Web ou un équilibrage de charge unique**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-120">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="07aa1-121">Dans la page sécurité de la **connexion au serveur** , sélectionnez **utiliser SSL pour se connecter au serveur Web publié ou à la batterie de**serveurs.</span><span class="sxs-lookup"><span data-stu-id="07aa1-121">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="07aa1-122">Dans la page Détails de la **publication interne** , dans **nom du site interne**, tapez le nom de domaine complet (FQDN) de votre pool de répertoires (par exemple, lyncdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="07aa1-122">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="07aa1-123">Si vous créez une règle pour l’URL des services Web externes sur le pool frontal, tapez l’adresse VIP de l’équilibrage de charge matérielle (HLB) en face du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="07aa1-123">If you are creating a rule for the external Web Services URL on the Front End pool, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="07aa1-124">Dans la page Détails de la **publication interne** , dans **Path (facultatif)**, tapez \*\* / \*\* le chemin d’accès du dossier à publier, puis sélectionnez **transférer l’en-tête d’hôte d’origine**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-124">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="07aa1-125">Dans la page **Détails du nom public** , procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="07aa1-125">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="07aa1-126">Sous **accepter les demandes pour**, sélectionnez **ce nom de domaine**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-126">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="07aa1-127">Dans **nom public**, tapez **lyncdiscover.** \<SIPDOMAIN\> (URL du service de découverte automatique externe).</span><span class="sxs-lookup"><span data-stu-id="07aa1-127">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="07aa1-128">Si vous créez une règle pour l’URL des services Web externes sur le pool frontal, tapez le nom de domaine complet (FQDN) pour les services Web externes dans votre liste frontale (par exemple, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="07aa1-128">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="07aa1-129">Dans **path**, tapez \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="07aa1-129">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="07aa1-130">Dans la page **Sélectionner** un écouteur Web, dans **écouteur Web**, sélectionnez votre écouteur SSL existant avec le certificat public mis à jour.</span><span class="sxs-lookup"><span data-stu-id="07aa1-130">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="07aa1-131">Dans la page **délégation d’authentification** , sélectionnez **aucune délégation, mais le client pourra s’authentifier directement**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-131">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="07aa1-132">Dans la page **jeu d’utilisateurs** , sélectionnez tous les **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-132">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="07aa1-133">Dans la page **fin de l’Assistant Nouvelle règle de publication Web** , vérifiez que les paramètres de règle de publication Web sont corrects, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-133">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="07aa1-134">Dans la liste de règles de publication Web de Forefront TMG, double-cliquez sur la nouvelle règle que vous venez d’ajouter pour ouvrir les **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-134">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="07aa1-135">Dans l’onglet **à** , procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="07aa1-135">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="07aa1-136">Sélectionnez **transférer l’en-tête d’hôte d’origine au lieu du premier**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-136">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="07aa1-137">**Les demandes de sélection semblent provenir de l’ordinateur Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-137">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="07aa1-138">Dans l’onglet **pontage** , configurez les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="07aa1-138">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="07aa1-139">Sélectionnez **serveur Web**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-139">Select **Web server**.</span></span>
    
      - <span data-ttu-id="07aa1-140">Sélectionnez **Rediriger les demandes vers le port http**et tapez **8080** pour le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="07aa1-140">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="07aa1-141">Sélectionnez **Rediriger les demandes vers le port SSL**et tapez **4443** pour le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="07aa1-141">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="07aa1-142">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-142">Click **OK**.</span></span>

18. <span data-ttu-id="07aa1-143">Cliquez sur **appliquer** dans le volet Détails pour enregistrer les modifications et mettre à jour la configuration.</span><span class="sxs-lookup"><span data-stu-id="07aa1-143">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="07aa1-144">Cliquez sur **règle de test** pour vérifier que la configuration de votre nouvelle règle est correcte.</span><span class="sxs-lookup"><span data-stu-id="07aa1-144">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="07aa1-145">Pour modifier une règle de publication sur le Web existante pour ajouter le SAN de découverte automatique et l’URL externes</span><span class="sxs-lookup"><span data-stu-id="07aa1-145">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="07aa1-146">Cliquez sur **Démarrer**, pointez sur **programmes**, sur **Microsoft Forefront TMG**, puis cliquez sur gestion de **Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-146">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="07aa1-147">Vous devrez répéter la modification pour chaque règle de publication et votre écouteur.</span><span class="sxs-lookup"><span data-stu-id="07aa1-147">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="07aa1-148">En règle générale, il s’agit d’une règle et d’un écouteur pour les pools frontaux et l’un pour les directeurs ou pools de directeurs facultatifs, si vous les avez déployés.</span><span class="sxs-lookup"><span data-stu-id="07aa1-148">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="07aa1-149">Dans le volet gauche, développez **NomServeur**, cliquez avec le bouton droit sur **stratégie de pare-feu**, puis cliquez sur la règle applicable.</span><span class="sxs-lookup"><span data-stu-id="07aa1-149">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule.</span></span> <span data-ttu-id="07aa1-150">Sous l’onglet **tâches** , cliquez sur **modifier la règle sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-150">On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="07aa1-151">Dans l’onglet **nom du public** , dans **cette règle**, sélectionnez **demandes pour les sites Web suivants**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-151">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="07aa1-152">Cliquez sur **Ajouter**, tapez le nom du nouveau site de découverte automatique (par exemple, «lyncdiscover.contoso.com»), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-152">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="07aa1-153">Dans l' \*\*\*\* onglet écouteur, cliquez sur **Sélectionner un certificat** et attribuez le nouveau certificat aux entrées du réseau de découverte automatique ajoutées.</span><span class="sxs-lookup"><span data-stu-id="07aa1-153">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries.</span></span> <span data-ttu-id="07aa1-154">Fermez les propriétés Listener et de publication Web.</span><span class="sxs-lookup"><span data-stu-id="07aa1-154">Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="07aa1-155">Cliquez sur **appliquer** dans le volet Détails pour enregistrer les modifications et mettre à jour la configuration.</span><span class="sxs-lookup"><span data-stu-id="07aa1-155">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="07aa1-156">Cliquez sur **règle de test** pour vérifier que la configuration de votre nouvelle règle est correcte.</span><span class="sxs-lookup"><span data-stu-id="07aa1-156">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="07aa1-157">Pour créer une règle de publication Web pour le port 80</span><span class="sxs-lookup"><span data-stu-id="07aa1-157">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="07aa1-158">Cliquez sur **Démarrer**, pointez sur **programmes**, sur **Microsoft Forefront TMG**, puis cliquez sur gestion de **Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-158">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="07aa1-159">Dans le volet gauche, développez **NomServeur**, cliquez avec le bouton droit sur **stratégie de pare-feu**, pointez sur **nouveau**, puis cliquez sur règle de **publication de site Web**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-159">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="07aa1-160">Dans la page **Bienvenue dans la nouvelle règle de publication Web** , tapez un nom d’affichage pour la nouvelle règle de publication (par exemple, la découverte automatique LYNC (http)).</span><span class="sxs-lookup"><span data-stu-id="07aa1-160">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="07aa1-161">Dans la page **Sélectionner une action de règle** , sélectionnez **autoriser**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-161">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="07aa1-162">Dans la page **type de publication** , sélectionnez **publier un site Web ou un équilibrage de charge unique**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-162">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="07aa1-163">Dans la page sécurité de la **connexion au serveur** , sélectionnez utiliser des **connexions non sécurisées pour la connexion au serveur Web publié ou à la batterie de serveurs**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-163">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="07aa1-164">Dans la page Détails de la **publication interne** , dans **nom du site interne**, tapez l’adresse VIP de l’équilibrage de charge matérielle (HLB) en face du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="07aa1-164">On the **Internal Publishing Details** page, in **Internal Site name**, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="07aa1-165">Dans la page Détails de la **publication interne** , dans **Path (facultatif)**, tapez \*\* / \*\* le chemin d’accès du dossier à publier, puis sélectionnez \*\*transférer l’en-tête d’hôte d’origine au lieu de celle spécifiée dans le champ nom du site interne. \*\*.</span><span class="sxs-lookup"><span data-stu-id="07aa1-165">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="07aa1-166">Dans la page **Détails du nom public** , procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="07aa1-166">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="07aa1-167">Sous **accepter les demandes pour**, sélectionnez **ce nom de domaine**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-167">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="07aa1-168">Dans **nom public**, tapez **lyncdiscover.** \<SIPDOMAIN\> (URL du service de découverte automatique externe).</span><span class="sxs-lookup"><span data-stu-id="07aa1-168">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="07aa1-169">Dans **path**, tapez \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="07aa1-169">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="07aa1-170">Dans la page **Sélectionner** un écouteur Web, dans **écouteur Web**, sélectionnez un écouteur Web ou utilisez l’Assistant Nouvelle définition de l’écouteur Web pour en créer un autre.</span><span class="sxs-lookup"><span data-stu-id="07aa1-170">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="07aa1-171">Dans la page **délégation d’authentification** , sélectionnez **aucune délégation, et le client ne peut pas s’authentifier directement**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-171">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="07aa1-172">Dans la page **jeu d’utilisateurs** , sélectionnez tous les **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-172">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="07aa1-173">Dans la page **fin de l’Assistant Nouvelle règle de publication Web** , vérifiez que les paramètres de règle de publication Web sont corrects, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-173">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="07aa1-174">Dans la liste de règles de publication Web de Forefront TMG, double-cliquez sur la nouvelle règle que vous venez d’ajouter pour ouvrir les **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-174">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="07aa1-175">Dans l’onglet **pontage** , configurez les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="07aa1-175">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="07aa1-176">Sélectionnez **serveur Web**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-176">Select **Web server**.</span></span>
    
      - <span data-ttu-id="07aa1-177">Sélectionnez **Rediriger les demandes vers le port http**et tapez **8080** pour le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="07aa1-177">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="07aa1-178">Vérifiez que l’option rediriger les **demandes vers le port SSL** n’est pas sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="07aa1-178">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="07aa1-179">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="07aa1-179">Click **OK**.</span></span>

17. <span data-ttu-id="07aa1-180">Cliquez sur **appliquer** dans le volet Détails pour enregistrer les modifications et mettre à jour la configuration.</span><span class="sxs-lookup"><span data-stu-id="07aa1-180">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="07aa1-181">Cliquez sur **règle de test** pour vérifier que la configuration de votre nouvelle règle est correcte.</span><span class="sxs-lookup"><span data-stu-id="07aa1-181">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="07aa1-182">Vérifiez que l’URL du service de découverte automatique externe n’est pas définie sur une autre règle de publication Web.</span><span class="sxs-lookup"><span data-stu-id="07aa1-182">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="07aa1-183">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07aa1-183">See Also</span></span>


[<span data-ttu-id="07aa1-184">Configuration des serveurs proxy inverses pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07aa1-184">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[<span data-ttu-id="07aa1-185">Exigences techniques pour la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07aa1-185">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

