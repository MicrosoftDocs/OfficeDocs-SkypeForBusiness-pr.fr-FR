---
title: 'Lync Server 2013: création ou modification d’un flux de travail de groupe de recherche'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c927b10107626c1d40c33290b30f331f660e45e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a><span data-ttu-id="acc90-102">Création ou modification d’un flux de travail de groupe de recherche dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acc90-102">Create or modify a hunt group workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acc90-103">_**Dernière modification de la rubrique:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="acc90-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="acc90-104">Pour créer ou modifier un flux de travail de groupe de recherche, utilisez l’une des procédures suivantes.</span><span class="sxs-lookup"><span data-stu-id="acc90-104">Use one of the following procedures to create or modify a hunt group workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="acc90-105">Vous pouvez utiliser Lync Server Management Shell ou l’outil de configuration de Response Group pour créer et modifier des flux de travail de groupe de recherche.</span><span class="sxs-lookup"><span data-stu-id="acc90-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify hunt group workflows.</span></span> <span data-ttu-id="acc90-106">Vous pouvez accéder à l’outil de configuration de Response Group à partir du panneau de configuration de Lync Server ou en ouvrant la page Web directement à partir d’un navigateur Web en tapant l’URL suivante: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="acc90-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="acc90-107">Pour utiliser l’outil de configuration de groupe de réponse pour créer ou modifier un flux de travail de groupe de recherche</span><span class="sxs-lookup"><span data-stu-id="acc90-107">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="acc90-108">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="acc90-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="acc90-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="acc90-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="acc90-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="acc90-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="acc90-111">Dans la barre de navigation de gauche, cliquez sur **Services Response Group**, puis sur **Flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="acc90-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="acc90-112">Dans la page **Flux de travail**, cliquez sur **Créer ou modifier un flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="acc90-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="acc90-113">Dans le champ de recherche **Sélectionner un service**, tapez entièrement ou partiellement le nom du service **ApplicationServer** qui héberge le flux de travail à créer ou à modifier.</span><span class="sxs-lookup"><span data-stu-id="acc90-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="acc90-114">Dans la liste des services obtenus, cliquez sur le service de votre choix, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="acc90-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acc90-115">L’outil de configuration de Response Group s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="acc90-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="acc90-116">Vous pouvez également ouvrir l’outil de configuration de groupe de réponse directement à partir d’un navigateur Web en tapant l’URL suivante: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="acc90-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="acc90-117">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="acc90-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="acc90-118">Sous **Créer un flux de travail**, en regard de **Groupe de recherche, cliquez sur Créer**.</span><span class="sxs-lookup"><span data-stu-id="acc90-118">Under **Create a New Workflow**, next to **Hunt Group, click Create**.</span></span>
    
      - <span data-ttu-id="acc90-119">Sous **Gérer un flux de travail existant**, recherchez le flux de travail à modifier, puis sous **Action**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="acc90-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="acc90-120">Si vous êtes prêt et que les utilisateurs peuvent commencer à appeler le flux de travail, activez la case à cocher **Activer le flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="acc90-120">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acc90-p105">Si vous créez un flux de travail géré, vous devez sélectionner <STRONG>Activer le flux de travail</STRONG>. Une fois que vous avez enregistré le flux de travail géré actif, vous pouvez le modifier et le désactiver.</span><span class="sxs-lookup"><span data-stu-id="acc90-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="acc90-123">Pour autoriser les utilisateurs fédérés à appeler le groupe, activez la case à cocher **Activer pour la fédération**.</span><span class="sxs-lookup"><span data-stu-id="acc90-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="acc90-124">Vous devez également disposer d’une stratégie d’accès externe qui s’applique à l’application de Response Group configurée pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="acc90-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acc90-125">La stratégie d’accès externe globale s’applique à l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="acc90-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="acc90-126">Vous pouvez configurer la stratégie globale pour la Fédération de groupe de réponse en utilisant le panneau de configuration de Lync Server ou en utilisant l’applet de commande <STRONG>Set-CsExternalAccessPolicy</STRONG> pour définir le paramètre EnableOutsideAccess sur true.</span><span class="sxs-lookup"><span data-stu-id="acc90-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="acc90-127">Gardez à l’esprit que les paramètres de stratégie globale s’appliquent à tous les utilisateurs sauf s’ils sont affectés à un site ou une stratégie d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="acc90-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="acc90-128">Par conséquent, avant de modifier ce paramètre pour les groupes Response Group, assurez-vous que le paramètre de fédération satisfait les exigences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="acc90-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="acc90-129">Pour plus d’informations sur l’application des stratégies aux utilisateurs, voir <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gérer une stratégie d’accès externe dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="acc90-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="acc90-130">Pour plus d’informations sur le paramètre de Fédération, voir <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="acc90-130">For details about the federation setting, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acc90-131">Les utilisateurs hébergés sur Lync Online ne peuvent pas passer d’appels vers des groupes de réponse hébergés dans un déploiement local.</span><span class="sxs-lookup"><span data-stu-id="acc90-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="acc90-132">C’est vrai dans les déploiements hybrides et dans les cas où un déploiement local est fédéré avec un déploiement Lync Online.</span><span class="sxs-lookup"><span data-stu-id="acc90-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="acc90-133">Pour masquer l’identité des agents pendant les appels, activez la case à cocher **Activer l’anonymat de l’agent**.</span><span class="sxs-lookup"><span data-stu-id="acc90-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acc90-p109">Les appels anonymes ne peuvent pas commencer par la messagerie instantanée ou la vidéo, mais l’agent ou l’appelant peut ajouter la messagerie instantanée et la vidéo une fois que l’appel a commencé. Un agent anonyme peut également mettre des appels en attente, transférer des appels (transferts invisibles et consultatifs), mais aussi parquer et récupérer des appels. Les appels anonymes ne prennent pas en charge la conférence, le partage d’application, le partage du Bureau, le transfert de fichiers, le tableau blanc, la collaboration de données et l’enregistrement d’appel. Les agents utilisant le plugin Lync VDI peuvent recevoir des appels entrants anonymes, mais ils ne peuvent pas effectuer d’appels sortants anonymes.</span><span class="sxs-lookup"><span data-stu-id="acc90-p109">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established. An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls. Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording. Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="acc90-138">Sous **Entrez l’adresse du groupe qui recevra les appels**, cliquez sur l’adresse URI SIP (Session Initiation Protocol) principale du groupe qui doit prendre les appels vers le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="acc90-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acc90-139">L’URI principal pour un flux de travail définit les modalités d’identification et de référencement du flux de travail.</span><span class="sxs-lookup"><span data-stu-id="acc90-139">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="acc90-140">L’URI SIP que vous entrez est créé en tant qu’objet de contact dans les services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="acc90-140">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="acc90-141">Pour créer l’URI, l’objet doit être unique dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="acc90-141">To create the URI, the object must be unique in Active Directory.</span></span>

    
    </div>

11. <span data-ttu-id="acc90-142">Dans **nom complet**, tapez le nom que vous voulez afficher pour le flux de travail (par exemple, groupe réponse vente).</span><span class="sxs-lookup"><span data-stu-id="acc90-142">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acc90-143">N’incluez pas les&lt;caractères «»&gt;ou «» dans le nom d’affichage.</span><span class="sxs-lookup"><span data-stu-id="acc90-143">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="acc90-144">N’utilisez pas les noms d’affichage ci-dessous, car ils sont réservés : <STRONG>RGS Presence Watcher</STRONG> ou <STRONG>Service d’annonce</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="acc90-144">Do not use the following display names because they are reserved: <STRONG>RGS Presence Watcher</STRONG> or <STRONG>Announcement Service</STRONG>.</span></span>

    
    </div>

12. <span data-ttu-id="acc90-145">Sous **Numéro de téléphone**, tapez l’URI de ligne pour le groupe Response Group (par exemple, +14255550165).</span><span class="sxs-lookup"><span data-stu-id="acc90-145">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="acc90-146">Dans **Numéro affiché**, tapez le numéro tel qu’il doit s’afficher pour le groupe Response Group (par exemple, +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="acc90-146">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="acc90-147">Facultatif Dans **Description**, tapez une description pour le flux de travail tel que vous voulez qu’il apparaisse sur la carte de visite dans le client Lync.</span><span class="sxs-lookup"><span data-stu-id="acc90-147">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Lync client.</span></span>

15. <span data-ttu-id="acc90-148">Dans **Type de flux de travail**, sélectionnez **Géré** si ce flux de travail sera géré par un responsable de groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="acc90-148">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="acc90-149">Pour affecter des responsables de groupe de réponse au flux de travail, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="acc90-149">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="acc90-150">Tapez l’URI SIP (Session Initiation Protocol) d’un responsable pour ce flux de travail, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="acc90-150">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>
    
    2.  <span data-ttu-id="acc90-151">Tapez l’URI SIP (Session Initiation Protocol) d’autres responsables à ajouter au flux de travail, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="acc90-151">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="acc90-p113">Tous les utilisateurs désignés comme responsables d’un groupe Response Group doivent posséder le rôle CsResponseGroupManager. Si les utilisateurs n’ont pas ce rôle, ils ne peuvent pas gérer les groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="acc90-p113">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="acc90-154">Dans **Étape 2 Sélection d’une langue**, cliquez sur la langue à utiliser pour la reconnaissance vocale et la conversion de texte par synthèse vocale.</span><span class="sxs-lookup"><span data-stu-id="acc90-154">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="acc90-155">Si vous souhaitez configurer un message de bienvenue, dans **Étape 3 Configuration d’un message de bienvenue**, activez la case à cocher **Lisez un message de bienvenue**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="acc90-155">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="acc90-156">Pour entrer le message de bienvenue sous forme de texte converti en message vocal pour les appelants, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message de bienvenue dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="acc90-156">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="acc90-157">N’incluez pas de balises HTML dans le texte que vous entrez.</span><span class="sxs-lookup"><span data-stu-id="acc90-157">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="acc90-158">Si vous incluez des balises HTML, vous recevrez un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="acc90-158">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="acc90-p115">Pour utiliser un enregistrement de fichier son (.wav) ou audio Windows Media (.wma) pour le message de bienvenue, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier audio à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="acc90-p115">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="acc90-163">Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères.</span><span class="sxs-lookup"><span data-stu-id="acc90-163">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="acc90-164">Pour plus d’informations sur les formats de fichiers pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">configuration technique requise pour Response Group dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="acc90-164">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="acc90-165">Dans **Étape 4 Spécification de vos heures d’ouverture**, dans la zone **Votre fuseau horaire**, sélectionnez le fuseau horaire du flux de travail.</span><span class="sxs-lookup"><span data-stu-id="acc90-165">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acc90-p117">Il s’agit du fuseau horaire des appelants et des agents du flux de travail. Il est utilisé pour calculer les heures d’ouverture et de fermeture. Par exemple, si le flux de travail est configuré pour utiliser le fuseau horaire Est de l’Amérique du Nord et que l’ouverture et la fermeture du flux de travail sont planifiées respectivement pour 7 heures et 23 heures, il s’agit de l’heure d’ouverture 7:00 Est et de l’heure de fermeture 23:00 Est. (Vous devez entrer les heures au format 24 heures.)</span><span class="sxs-lookup"><span data-stu-id="acc90-p117">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="acc90-171">Sélectionnez le type d’heures d’ouverture à utiliser en effectuant l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="acc90-171">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="acc90-172">Pour utiliser un planning prédéfini d’heures d’ouverture, cliquez sur **Utiliser un planning prédéfini**, puis sélectionnez le planning souhaité dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="acc90-172">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="acc90-173">Pour sélectionner cette option, vous devez avoir défini précédemment au moins un planning prédéfini.</span><span class="sxs-lookup"><span data-stu-id="acc90-173">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="acc90-174">Vous pouvez spécifier des plannings prédéfinis à l’aide de l’applet de commande <STRONG>New-CSRgsHoursOfBusiness</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="acc90-174">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="acc90-175">Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-optional-define-response-group-business-hours.md">définir les heures d’activité du groupe de réponses dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="acc90-175">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="acc90-176">Lorsque vous sélectionnez un planning prédéfini, les champs <STRONG>Jour</STRONG>, <STRONG>Ouverture</STRONG> et <STRONG>Fermeture</STRONG> sont renseignés automatiquement avec les jours et les heures de disponibilité du groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="acc90-176">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="acc90-177">Pour utiliser un planning personnalisé qui ne s’applique qu’à ce flux de travail, cliquez sur **Utiliser un planning personnalisé**.</span><span class="sxs-lookup"><span data-stu-id="acc90-177">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="acc90-178">Si vous créez un planning personnalisé pour ce flux de travail, activez les cases à cocher correspondant aux jours de la semaine pendant lesquels le groupe Response Group est disponible.</span><span class="sxs-lookup"><span data-stu-id="acc90-178">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="acc90-179">Si vous créez un planning personnalisé, tapez les heures d’**ouverture** et de **fermeture** pour chaque jour de la semaine pendant lesquelles le groupe Response Group est disponible.</span><span class="sxs-lookup"><span data-stu-id="acc90-179">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acc90-p119">Les heures <STRONG>Ouverture</STRONG> et <STRONG>Fermeture</STRONG> doivent être au format 24 heures. Par exemple, si votre bureau est ouvert de 9 heures à 17 heures et fermé à midi pour le déjeuner, les heures d’ouverture sont spécifiées comme suit : <STRONG>Ouverture</STRONG> 9:00, <STRONG>Fermeture</STRONG> 12:00, <STRONG>Ouverture</STRONG> 13:00 et <STRONG>Fermeture</STRONG> 17:00.</span><span class="sxs-lookup"><span data-stu-id="acc90-p119">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="acc90-182">Si vous souhaitez que la lecture d’un message se déclenche lorsque le bureau est fermé, activez la case à cocher **Lisez un message lorsque le service Response Group est en dehors des heures d’ouverture**, puis spécifiez le message à lire en effectuant l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="acc90-182">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="acc90-183">Pour entrer le message sous forme de texte converti en message vocal pour l’appelant, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="acc90-183">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="acc90-p120">N’incluez pas de balises HTML dans le texte que vous entrez. Si vous incluez des balises HTML, vous recevrez un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="acc90-p120">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="acc90-p121">Pour utiliser un enregistrement de fichier audio pour le message, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="acc90-p121">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="acc90-190">Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères.</span><span class="sxs-lookup"><span data-stu-id="acc90-190">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="acc90-191">Pour plus d’informations sur les formats de fichiers audio pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">configuration technique requise pour Response Group dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="acc90-191">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="acc90-192">Spécifiez comment gérer les appels après la lecture du message (si un message est configuré) :</span><span class="sxs-lookup"><span data-stu-id="acc90-192">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="acc90-193">Pour déconnecter l’appel, cliquez sur **Déconnecter l’appel**.</span><span class="sxs-lookup"><span data-stu-id="acc90-193">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="acc90-194">Pour transférer l’appel vers la messagerie vocale, cliquez sur **Transférer à la messagerie vocale**, puis tapez l’adresse de la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="acc90-194">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="acc90-195">Le format de l’adresse de messagerie vocale \<est\>@\<nom\> d’utilisateur nom_domaine (par exemple, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="acc90-195">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="acc90-196">Pour transférer l’appel vers un autre utilisateur, cliquez sur **Transférer à l’URI SIP**, puis tapez l’adresse de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="acc90-196">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="acc90-197">Le format de l’adresse utilisateur est \<nom\>@\<d'\>utilisateur nom_domaine.</span><span class="sxs-lookup"><span data-stu-id="acc90-197">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="acc90-198">Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **Transférer au numéro de téléphone**, puis tapez le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="acc90-198">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="acc90-199">Le format de numéro de téléphone est \<le\>@\<numéro\> nom_domaine (par exemple, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="acc90-199">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="acc90-200">Le nom de domaine est utilisé pour router l’appelant vers la destination appropriée.</span><span class="sxs-lookup"><span data-stu-id="acc90-200">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="acc90-201">Dans **Étape 5 Spécification de vos congés**, activez les cases à cocher correspondant à une ou plusieurs périodes de congés définissant les jours de fermeture du groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="acc90-201">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acc90-202">Vous devez définir les congés et les périodes de congé avant de configurer le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="acc90-202">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="acc90-203">Utilisez les applets de commande <STRONG>New-CsRgsHoliday</STRONG> et <STRONG>New-CsRgsHolidaySet</STRONG> pour créer des congés et des périodes de congé.</span><span class="sxs-lookup"><span data-stu-id="acc90-203">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="acc90-204">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">définir (facultatif) des jeux de vacances de groupe de réponses dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="acc90-204">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="acc90-205">Si vous souhaitez que la lecture d’un message se déclenche pendant les congés, activez la case à cocher **Lisez un message pendant les congés**, puis spécifiez le message à lire en effectuant l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="acc90-205">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="acc90-206">Pour entrer le message sous forme de texte converti en message vocal pour l’appelant, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="acc90-206">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="acc90-p127">N’incluez pas de balises HTML dans le texte que vous entrez. Si vous incluez des balises HTML, vous recevrez un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="acc90-p127">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="acc90-p128">Pour utiliser un enregistrement de fichier audio pour le message, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="acc90-p128">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="acc90-213">Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères.</span><span class="sxs-lookup"><span data-stu-id="acc90-213">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="acc90-214">Pour plus d’informations sur les formats de fichiers audio pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">configuration technique requise pour Response Group dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="acc90-214">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="acc90-215">Spécifiez comment gérer les appels après la lecture du message (si un message est configuré) :</span><span class="sxs-lookup"><span data-stu-id="acc90-215">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="acc90-216">Pour déconnecter l’appel, cliquez sur **Déconnecter l’appel**.</span><span class="sxs-lookup"><span data-stu-id="acc90-216">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="acc90-217">Pour transférer l’appel vers la messagerie vocale, cliquez sur **Transférer à la messagerie vocale**, puis tapez l’adresse de la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="acc90-217">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="acc90-218">Le format de l’adresse de messagerie vocale \<est\>@\<nom\> d’utilisateur nom_domaine (par exemple, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="acc90-218">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="acc90-219">Pour transférer l’appel vers un autre utilisateur, cliquez sur **Transférer à l’URI SIP**, puis tapez l’adresse de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="acc90-219">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="acc90-220">Le format de l’adresse utilisateur est \<nom\>@\<d'\>utilisateur nom_domaine.</span><span class="sxs-lookup"><span data-stu-id="acc90-220">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="acc90-221">Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **Transférer au numéro de téléphone**, puis tapez le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="acc90-221">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="acc90-222">Le format de numéro de téléphone est \<le\>@\<numéro\> nom_domaine (par exemple, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="acc90-222">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="acc90-223">Le nom de domaine est utilisé pour router l’appelant vers la destination appropriée.</span><span class="sxs-lookup"><span data-stu-id="acc90-223">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="acc90-224">Dans **Étape 6 Configuration d’une file d’attente**, dans **Sélectionnez la file d’attente qui reçoit les appels**, sélectionnez la file d’attente dans laquelle mettre les appelants en attendant qu’un agent soit disponible.</span><span class="sxs-lookup"><span data-stu-id="acc90-224">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="acc90-225">Dans **Étape 7 Configuration d’une attente musicale**, choisissez la musique que les appelants entendront pendant qu’ils attendent un agent. Pour cela, procédez de l’une des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="acc90-225">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="acc90-226">Pour utiliser l’enregistrement d’attente musicale par défaut, cliquez sur **Utiliser la valeur par défaut**.</span><span class="sxs-lookup"><span data-stu-id="acc90-226">To use the default music-on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="acc90-p133">Pour utiliser un enregistrement de fichier audio pour l’attente musicale, cliquez sur **Sélectionner un fichier de musique**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un fichier de musique**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="acc90-p133">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="acc90-231">Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères.</span><span class="sxs-lookup"><span data-stu-id="acc90-231">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="acc90-232">Pour plus d’informations sur les formats de fichiers audio pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">configuration technique requise pour Response Group dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="acc90-232">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="acc90-233">Cliquez sur **Déployer**.</span><span class="sxs-lookup"><span data-stu-id="acc90-233">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="acc90-234">Pour utiliser Windows PowerShell afin de créer ou de modifier un flux de travail de groupe de recherche</span><span class="sxs-lookup"><span data-stu-id="acc90-234">To use Windows PowerShell to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="acc90-235">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="acc90-235">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="acc90-236">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="acc90-236">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="acc90-p135">Créez l’invite à exécuter pour le message de bienvenue, et enregistrez-la dans une variable. Dans la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="acc90-p135">Create the prompt to be played for the welcome message, and save it in a variable. At the command line, run:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="acc90-239">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="acc90-239">For example:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acc90-240">Pour utiliser un fichier audio pour l’invite, utilisez l’applet de commande <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="acc90-240">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="acc90-241">Pour plus d’informations, voir <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="acc90-241">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="acc90-242">Obtenez l’identité de la file d’attente ou demandez où les appels seront dirigés.</span><span class="sxs-lookup"><span data-stu-id="acc90-242">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="acc90-243">Dans la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="acc90-243">At the command line, run:</span></span>
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    <span data-ttu-id="acc90-244">Pour plus d’informations sur la création de la file d’attente, voir [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span><span class="sxs-lookup"><span data-stu-id="acc90-244">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span></span>

5.  <span data-ttu-id="acc90-p138">Définissez l’action par défaut à effectuer lorsqu’un flux de travail est ouvert pendant les heures ouvrées et enregistrez-la dans une variable. Dans la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="acc90-p138">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable. At the command line, run:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acc90-p139">Pour les flux de travail de groupe de recherche, l’action par défaut doit rediriger l’appel vers une file d’attente. Ce paramètre est obligatoire pour les flux de travail actifs. Il ne l’est pas pour les flux de travail inactifs.</span><span class="sxs-lookup"><span data-stu-id="acc90-p139">For hunt group workflows, the default action must direct the call to a queue. This is parameter is required for active workflows. It is not required for inactive workflows.</span></span>

    
    </div>
    
    <span data-ttu-id="acc90-250">Exemple :</span><span class="sxs-lookup"><span data-stu-id="acc90-250">For example:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  <span data-ttu-id="acc90-251">Si vous voulez définir des heures ouvrées et des congés, vous devez les créer avant de créer et modifier le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="acc90-251">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="acc90-252">Pour plus d’informations, reportez-vous à la section [définir les heures d’activité du groupe de réponses dans Lync server 2013](lync-server-2013-optional-define-response-group-business-hours.md) et [(facultatif) définir les jeux de vacances du groupe réponse dans Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span><span class="sxs-lookup"><span data-stu-id="acc90-252">For details, see [(Optional) Define Response Group business hours in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span></span>

7.  <span data-ttu-id="acc90-253">Pour avoir des invites pour les appels reçus en dehors des heures ouvrées ou pendant des congés, utilisez l’applet de commande **New-CsRgsPrompt** pour définir l’invite et **New-CsRgsCallAction** pour définir l’action à effectuer après l’invite.</span><span class="sxs-lookup"><span data-stu-id="acc90-253">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="acc90-254">Pour plus d’informations, reportez-vous à [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) et [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span><span class="sxs-lookup"><span data-stu-id="acc90-254">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span></span>

8.  <span data-ttu-id="acc90-255">Récupérez le nom du service pour le service du groupe de réponses du serveur Lync et attribuez-le à une variable.</span><span class="sxs-lookup"><span data-stu-id="acc90-255">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="acc90-256">Dans la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="acc90-256">At the command, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  <span data-ttu-id="acc90-257">Créez ou modifiez le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="acc90-257">Create or modify the workflow.</span></span> <span data-ttu-id="acc90-258">Pour créer un flux de travail, utilisez **New-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="acc90-258">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="acc90-259">Pour modifier un flux de travail, utilisez **Set-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="acc90-259">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="acc90-260">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="acc90-260">At the command line, type:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    <span data-ttu-id="acc90-261">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="acc90-261">For example:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="acc90-262">Tous les utilisateurs désignés comme responsables pour les flux de travail doivent posséder le rôle CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="acc90-262">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acc90-263">Pour plus d’informations sur les paramètres facultatifs supplémentaires, voir <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> ou <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span><span class="sxs-lookup"><span data-stu-id="acc90-263">For details about additional optional parameters, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> or <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="acc90-264">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="acc90-264">See Also</span></span>


[<span data-ttu-id="acc90-265">Facultatif Définir des jeux de vacances de groupe de réponse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acc90-265">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="acc90-266">Facultatif Définir les heures d’activité du groupe de réponses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acc90-266">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  


[<span data-ttu-id="acc90-267">Nouveau-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="acc90-267">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[<span data-ttu-id="acc90-268">Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="acc90-268">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[<span data-ttu-id="acc90-269">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="acc90-269">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="acc90-270">Nouveau-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="acc90-270">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

