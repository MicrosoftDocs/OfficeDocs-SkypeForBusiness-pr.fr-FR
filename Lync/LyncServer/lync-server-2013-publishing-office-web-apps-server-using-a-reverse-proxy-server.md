---
title: Publication d’Office Web Apps Server à l’aide d’un serveur proxy inverse
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
ms.openlocfilehash: 6964c111fa6ca7225c25884c52d02564314ececf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="4ba15-102">Publication d’Office Web Apps Server dans Lync Server 2013 à l’aide d’un serveur proxy inverse</span><span class="sxs-lookup"><span data-stu-id="4ba15-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ba15-103">_**Dernière modification de la rubrique :** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="4ba15-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="4ba15-104">Si vous souhaitez que les utilisateurs externes (c’est-à-dire, les utilisateurs qui se connectent depuis l’extérieur du pare-feu de votre organisation) aient accès aux présentations PowerPoint d’Office Web Apps Server, vous devez utiliser Office Web Apps Server et un serveur de proxy inverse tel que Microsoft Forefront Threat Management Gateway.</span><span class="sxs-lookup"><span data-stu-id="4ba15-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="4ba15-105">Cela signifie également que vous devrez créer et configurer une règle de publication de site Web ; Cette règle permet de s’assurer que les utilisateurs peuvent se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="4ba15-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="4ba15-106">Si vous n’avez pas besoin d’autoriser l’accès à des utilisateurs externes, vous n’avez pas besoin de configurer une telle règle.</span><span class="sxs-lookup"><span data-stu-id="4ba15-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="4ba15-107">Pour configurer une règle de publication de site web dans Forefront Threat Management Gateway, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4ba15-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="4ba15-108">Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Forefront TMG**, puis sur **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="4ba15-109">Dans Forefront TMG, cliquez avec le bouton droit sur **Stratégie de pare-feu**, pointez sur **Nouveau**, puis cliquez sur **Règle de publication de site web**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="4ba15-110">Dans l’Assistant Nouvelle règle de publication web, dans la page **Bienvenue dans l’Assistant Nouvelle règle de publication web**, tapez le nom de votre nouvelle règle dans la zone **Nom de la règle de publication web** (par exemple, **Règle Office Web Apps Server**), puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="4ba15-111">Dans la page **Spécifier l’action de la règle**, sélectionnez **Autoriser**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="4ba15-112">Dans la page **Type de publication**, sélectionnez **Publier un seul site web ou équilibreur de charge**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="4ba15-113">Dans la page **Sécurité de connexion serveur**, sélectionnez **Utiliser SSL pour se connecter au serveur web publié ou à la batterie de serveurs**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="4ba15-p102">Dans la page **Détails de la publication interne**, tapez le nom de domaine complet du serveur Office Web Apps (par exemple, **officewebapps01.contoso.com**) dans la zone **Nom de site local**, puis cliquez sur **Suivant**. Le nom entré dans la zone **Nom de site local** doit figurer dans le champ Sujet ou le champ Autre nom du sujet du certificat que vous avez affecté à Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="4ba15-p102">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**. The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="4ba15-116">Sur la page **Détails de publication interne** , \*\* / \*\* tapez dans la zone **chemin d’accès (facultatif)** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="4ba15-117">La\* syntaxe permet de s’assurer que tous les dossiers et sous-dossiers du site sont publiés.</span><span class="sxs-lookup"><span data-stu-id="4ba15-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="4ba15-118">Dans la page **Informations sur les noms publics**, sélectionnez **Ce nom de domaine (saisissez ci-dessous)** dans la zone déroulante **Accepter les demandes pour**, puis tapez le nom complet de votre serveur Office Web Apps Server dans la zone de nom public.</span><span class="sxs-lookup"><span data-stu-id="4ba15-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="4ba15-119">Ce nom doit être le même que le nom utilisé pour accéder à votre site web.</span><span class="sxs-lookup"><span data-stu-id="4ba15-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="4ba15-120">Par exemple, si vous accédez à votre site à l' http://officewebapps01.contoso.com aide de l’URL, entrez **officewebapps01.contoso.com** dans la zone **nom public** .</span><span class="sxs-lookup"><span data-stu-id="4ba15-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="4ba15-121">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-121">Click **Next**.</span></span>

11. <span data-ttu-id="4ba15-122">Dans la page **Sélectionnez le port d’écoute**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="4ba15-123">Dans l’Assistant Nouvelle définition de port d’écoute web, tapez le nom du nouveau port d’écoute web (par exemple, **SSL**) dans la zone **Nom du port d’écoute web**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="4ba15-124">Dans la page **Sécurité de la connexion cliente**, sélectionnez **Exiger les connexions sécurisées SSL avec les clients**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="4ba15-125">Dans la page **Adresses IP des ports d’écoute web**, sélectionnez **Externe**, sélectionnez **Interne**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="4ba15-126">Dans la page **Certificats SSL du port d’écoute**, sélectionnez **Utiliser un seul certificat pour ce port d’écoute web**, puis cliquez sur **Sélectionner le certificat**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="4ba15-127">Dans la boîte de dialogue **Sélectionner le certificat**, sélectionnez le certificat à utiliser pour ce port d’écoute web, puis cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="4ba15-128">Dans la page**Certificats SSL du port d’écoute**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="4ba15-129">Dans la page **Paramètres d’authentification**, sélectionnez **Aucune authentification** dans la liste déroulante **Sélectionner la méthode avec laquelle les clients fourniront les informations d’identification à Forefront TMG**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="4ba15-130">Dans la page **Paramètres de l’authentification unique**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="4ba15-p105">Dans la page **Fin de l’Assistant Nouveau port d’écoute web**, vérifiez le résumé de vos choix de configuration. Lorsque c’est fait, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-p105">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made. When ready, click **Finish**.</span></span>

21. <span data-ttu-id="4ba15-133">Dans la page **Sélectionnez le port d’écoute**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="4ba15-134">Dans la page **Délégation de l’authentification**, sélectionnez **Aucune délégation, mais le client peut s’authentifier directement** dans la liste déroulante **Sélectionner la méthode utilisée par Forefront TMG pour s’authentifier auprès du serveur web publié**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="4ba15-p106">Dans la page **Ensembles d’utilisateurs**, confirmez que les ensembles d’utilisateurs appropriés sont répertoriés. Par défaut, il s’agit de l’ensemble d’utilisateurs **Tous les utilisateurs**. Cliquez sur **Ajouter** pour ajouter les autres ensembles d’utilisateurs que vous avez éventuellement définis. Lorsque c’est fait, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-p106">On the **User Sets** page, confirm that the appropriate user sets are listed. By default, this is the **All Users** user set. Click **Add** to add other user sets you may have defined. When complete, click **Next**.</span></span>

24. <span data-ttu-id="4ba15-139">Dans la page **Fin de l’Assistant Nouvelle règle de publication web**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="4ba15-p107">Notez que le fait de cliquer sur **Terminer** ne signifie pas que vous avez terminé la procédure ; en d’autres termes, la nouvelle règle n’est pas automatiquement appliquée. En fait, vous devez cliquer sur le bouton **Appliquer** qui apparaît dans l’interface utilisateur de Forefront TMG. Lorsque vous cliquez sur **Appliquer**, la boîte de dialogue **Description de la modification de la configuration** s’affiche. Cliquez sur **Appliquer** dans cette boîte de dialogue pour activer la nouvelle règle de publication.</span><span class="sxs-lookup"><span data-stu-id="4ba15-p107">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule. Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface. When you click **Apply** the **Configuration Change Description** dialog box will appear. Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="4ba15-144">Une fois que votre nouvelle règle a été appliquée, vous devrez apporter quelques modifications mineures à la règle afin de garantir que les utilisateurs peuvent utiliser les nouvelles fonctionnalités de présentation PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="4ba15-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="4ba15-145">Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4ba15-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="4ba15-146">Dans Forefront TMG, cliquez avec le bouton droit sur le nom de la nouvelle règle de publication, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="4ba15-147">Dans la boîte de dialogue **Propriétés**, sous l’onglet **À**, sélectionnez l’option **Transmettre l’en-tête de l’hôte d’origine plutôt que l’en-tête réel**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="4ba15-148">Sous l’onglet **Trafic**, cliquez sur **Filtrage**, puis sur **Configurer HTTP**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="4ba15-149">Dans la boîte de dialogue **Configuration de la stratégie HTTP pour la règle**, désactivez la case à cocher **Vérifier la normalisation**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="4ba15-150">Dans la boîte de dialogue **Propriétés**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="4ba15-p109">Dans Forefront TMG, cliquez sur **Appliquer** pour appliquer les modifications. Lorsque la boîte de dialogue **Description de la modification de la configuration** s’affiche, cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="4ba15-p109">In Forefront TMG, click **Apply** to enable the changes. When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="4ba15-153">Une fois l’installation terminée, vous pouvez tester votre serveur Office Web Apps Server à l’aide des procédures décrites dans la rubrique [validation de la configuration d’Office Web Apps Server dans Lync server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span><span class="sxs-lookup"><span data-stu-id="4ba15-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

