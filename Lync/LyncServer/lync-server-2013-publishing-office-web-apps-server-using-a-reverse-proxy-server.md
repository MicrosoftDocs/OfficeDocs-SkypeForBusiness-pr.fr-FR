---
title: Publication d’Office Web Apps Server avec un serveur proxy inverse
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a81fff75adbeadb6cfcead3316dab2c89b4269
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="37228-102">Publication d’Office Web Apps Server dans Lync Server 2013 à l’aide d’un serveur proxy inverse</span><span class="sxs-lookup"><span data-stu-id="37228-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37228-103">_**Dernière modification de la rubrique :** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="37228-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="37228-104">Si vous souhaitez que les utilisateurs externes (c’est-à-dire, les utilisateurs qui se connectent à partir de l’extérieur du pare-feu de votre organisation) puissent accéder aux présentations PowerPoint sur Office Web Apps Server, vous devrez utiliser Office Web Apps Server et un serveur proxy inverse tel que Microsoft Forefront Passerelle de gestion des menaces.</span><span class="sxs-lookup"><span data-stu-id="37228-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="37228-105">Par ailleurs, vous devrez créer et configurer une règle de publication de site Web. Cette règle permet de garantir que les utilisateurs sont en mesure de se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="37228-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="37228-106">Si vous n’avez pas besoin de fournir un accès aux utilisateurs externes, vous n’avez pas besoin de configurer une règle de publication de site Web.</span><span class="sxs-lookup"><span data-stu-id="37228-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="37228-107">Pour configurer une règle de publication sur un site Web dans la passerelle gestion des menaces de Forefront, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="37228-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="37228-108">Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Forefront TMG**, puis sur gestion de **Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="37228-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="37228-109">Dans Forefront TMG, cliquez avec le bouton droit sur **stratégie de pare-feu**, pointez sur **nouveau**, puis cliquez sur **règle de publication de site Web**.</span><span class="sxs-lookup"><span data-stu-id="37228-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="37228-110">Dans l’Assistant Nouvelle règle de publication Web, dans la page **Bienvenue dans l’Assistant Nouvelle règle de publication Web** , tapez un nom pour votre nouvelle règle dans la zone nom de la **règle de publication Web** (par exemple, **Office Web Apps Server Rule**), puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="37228-111">Dans la page **spécifier une action de règle** , sélectionnez **autoriser** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="37228-112">Dans la page **type de publication** , sélectionnez **publier un site Web ou un équilibrage de charge** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="37228-113">Dans la page sécurité de la **connexion au serveur** , sélectionnez **utiliser SSL pour se connecter au serveur Web ou à la batterie** de serveurs publié, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="37228-114">Dans la page Détails de la **publication interne** , tapez le nom de domaine complet (FQDN) de votre serveur Office Web Apps (par exemple, **officewebapps01.contoso.com**) dans la zone **nom du site interne** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-114">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**.</span></span> <span data-ttu-id="37228-115">Le nom entré dans la zone **nom du site interne** doit apparaître dans le champ objet ou le champ autre nom de l’objet du certificat que vous avez attribué à Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="37228-115">The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="37228-116">Dans la page Détails de la **publication interne** , entrez \*\* / \*\* le **chemin d’accès (facultatif)** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="37228-117">La\* syntaxe permet de s’assurer que tous les dossiers et sous-dossiers du site sont publiés.</span><span class="sxs-lookup"><span data-stu-id="37228-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="37228-118">Dans la page **Détails du nom public** , sélectionnez **ce nom de domaine (tapez ci-dessous)** dans la liste déroulante **accepter les demandes pour** et tapez le nom complet de votre serveur Office Web Apps dans la zone Nom du public.</span><span class="sxs-lookup"><span data-stu-id="37228-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="37228-119">Ce nom doit être le nom utilisé pour accéder à votre site Web.</span><span class="sxs-lookup"><span data-stu-id="37228-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="37228-120">Par exemple, si vous accédez à votre site à l' http://officewebapps01.contoso.com aide de l’URL, entrez **officewebapps01.contoso.com** dans la zone **nom du public** .</span><span class="sxs-lookup"><span data-stu-id="37228-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="37228-121">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-121">Click **Next**.</span></span>

11. <span data-ttu-id="37228-122">Dans la page **Sélectionner un écouteur Web** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="37228-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="37228-123">Dans l’Assistant Nouvelle définition de l’écouteur Web, tapez un nom pour le nouvel écouteur Web (par exemple, **SSL**) dans la zone nom de l' **écouteur Web** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="37228-124">Dans la page **sécurité de connexion client** , sélectionnez **exiger des connexions SSL sécurisées avec les clients** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="37228-125">Dans la page **adresses IP de l’écouteur Web** , sélectionnez **externe**, sélectionnez **interne**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="37228-126">Sur la page **certificats SSL de l’écouteur** , sélectionnez **utiliser un certificat unique pour ce détecteur de site Web** , puis cliquez sur **Sélectionner un certificat**.</span><span class="sxs-lookup"><span data-stu-id="37228-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="37228-127">Dans la boîte de dialogue **Sélectionner un certificat** , sélectionnez le certificat que vous voulez utiliser pour ce détecteur Web, puis cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="37228-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="37228-128">Sur la page **certificats SSL de l’écouteur** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="37228-129">Dans la page **paramètres d’authentification** , sélectionnez **aucune authentification** dans la liste déroulante **Sélectionner la façon dont les clients fournissent des informations d’identification à l’aide de la liste déroulante Sélectionner la façon dont les clients doivent fournir des informations d’identification à** la \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="37228-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="37228-130">Dans la page **paramètres de connexion unique** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="37228-131">Dans la page **fin de l’Assistant Nouvelle écoute Web** , consultez le résumé des choix de configuration que vous avez effectués.</span><span class="sxs-lookup"><span data-stu-id="37228-131">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made.</span></span> <span data-ttu-id="37228-132">Lorsque vous êtes prêt, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="37228-132">When ready, click **Finish**.</span></span>

21. <span data-ttu-id="37228-133">Dans la page **Sélectionner un écouteur Web** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="37228-134">Dans la page **délégation d’authentification** , sélectionnez **aucune délégation, mais le client pourra s’authentifier directement** dans la liste déroulante **Sélectionner la méthode utilisée par Forefront TMG pour s’authentifier dans la** liste déroulante du serveur Web publié, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="37228-135">Dans la page **ensembles d’utilisateurs** , vérifiez que les jeux d’utilisateurs appropriés apparaissent.</span><span class="sxs-lookup"><span data-stu-id="37228-135">On the **User Sets** page, confirm that the appropriate user sets are listed.</span></span> <span data-ttu-id="37228-136">Par défaut, il s’agit de l’utilisateur **tous les utilisateurs** définis.</span><span class="sxs-lookup"><span data-stu-id="37228-136">By default, this is the **All Users** user set.</span></span> <span data-ttu-id="37228-137">Cliquez sur **Ajouter** pour ajouter d’autres jeux d’utilisateurs que vous avez éventuellement définis.</span><span class="sxs-lookup"><span data-stu-id="37228-137">Click **Add** to add other user sets you may have defined.</span></span> <span data-ttu-id="37228-138">Lorsque vous avez terminé, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="37228-138">When complete, click **Next**.</span></span>

24. <span data-ttu-id="37228-139">Dans la page **fin de l’Assistant Nouvelle règle de publication Web** , cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="37228-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="37228-140">Notez que le fait de cliquer sur **Terminer** ne signifie pas que vous avez terminé le processus. c’est-à-dire qu’elle n’est pas appliquée automatiquement et qu’elle est activée.</span><span class="sxs-lookup"><span data-stu-id="37228-140">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule.</span></span> <span data-ttu-id="37228-141">À la place, vous devrez cliquer sur le bouton **appliquer** qui s’affichera dans l’interface utilisateur de Forefront TMG.</span><span class="sxs-lookup"><span data-stu-id="37228-141">Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface.</span></span> <span data-ttu-id="37228-142">Lorsque vous cliquez sur **appliquer** , la boîte de dialogue Description de la **modification de configuration** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="37228-142">When you click **Apply** the **Configuration Change Description** dialog box will appear.</span></span> <span data-ttu-id="37228-143">Dans cette boîte de dialogue, cliquez sur **appliquer** pour activer la nouvelle règle de publication.</span><span class="sxs-lookup"><span data-stu-id="37228-143">Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="37228-144">Une fois votre nouvelle règle appliquée, vous devrez apporter quelques modifications mineures à la règle pour vous assurer que les utilisateurs peuvent utiliser les nouvelles fonctionnalités de présentation PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="37228-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="37228-145">Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="37228-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="37228-146">Dans Forefront TMG, cliquez avec le bouton droit sur le nom de la nouvelle règle de publication, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="37228-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="37228-147">Dans la boîte de dialogue **Propriétés** , sous l’onglet **à** , sélectionnez l’option **transférer l’en-tête d’hôte d’origine au lieu de l’en-tête réel**.</span><span class="sxs-lookup"><span data-stu-id="37228-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="37228-148">Dans l’onglet **trafic** , cliquez sur **filtrage** , puis sur **configurer http**.</span><span class="sxs-lookup"><span data-stu-id="37228-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="37228-149">Dans la boîte de dialogue Configuration de la **stratégie http pour la règle** , décochez la case **Vérifier la normalisation** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="37228-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="37228-150">Dans la boîte de dialogue **Propriétés** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="37228-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="37228-151">Dans Forefront TMG, cliquez sur **appliquer** pour activer les modifications.</span><span class="sxs-lookup"><span data-stu-id="37228-151">In Forefront TMG, click **Apply** to enable the changes.</span></span> <span data-ttu-id="37228-152">Lorsque la boîte de dialogue Description de la modification de la **configuration** s’affiche, cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="37228-152">When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="37228-153">À l’issue de l’installation, vous pouvez tester votre serveur Office Web Apps en suivant les procédures décrites dans la rubrique [vérification de la configuration d’Office Web Apps Server dans Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span><span class="sxs-lookup"><span data-stu-id="37228-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

