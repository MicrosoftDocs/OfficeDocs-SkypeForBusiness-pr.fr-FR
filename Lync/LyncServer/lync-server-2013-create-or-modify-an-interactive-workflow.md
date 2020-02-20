---
title: 'Lync Server 2013 : création ou modification d’un flux de travail interactif'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7173d739c66982d0995a478e086fee2442fcbd0b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="66c3d-102">Création ou modification d’un flux de travail interactif dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66c3d-102">Create or modify an interactive workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66c3d-103">_**Dernière modification de la rubrique :** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="66c3d-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="66c3d-104">En choisissant l’une des procédures suivantes, vous pouvez créer ou modifier un flux de travail interactif.</span><span class="sxs-lookup"><span data-stu-id="66c3d-104">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66c3d-105">Vous pouvez utiliser Lync Server Management Shell ou l’outil de configuration Response Group pour créer et modifier des flux de travail interactifs.</span><span class="sxs-lookup"><span data-stu-id="66c3d-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="66c3d-106">Vous pouvez accéder à l’outil de configuration Response Group à partir du panneau de configuration de Lync Server ou en ouvrant la page Web directement à partir d’un navigateur Web en tapant l’URL suivante : <STRONG>https://</STRONG>&lt;webpoolfqdn représente&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="66c3d-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="66c3d-107">Pour utiliser l’outil de configuration de Response Group pour créer ou modifier un flux de travail interactif</span><span class="sxs-lookup"><span data-stu-id="66c3d-107">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="66c3d-108">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="66c3d-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="66c3d-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66c3d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="66c3d-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="66c3d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="66c3d-111">Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis sur **Flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="66c3d-112">Sur la page **Flux de travail**, cliquez sur **Créer ou modifier un flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="66c3d-113">Dans le champ de recherche **Sélectionner un service**, tapez entièrement ou partiellement le nom du service **ApplicationServer** qui héberge le flux de travail à créer ou à modifier.</span><span class="sxs-lookup"><span data-stu-id="66c3d-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="66c3d-114">Dans la liste des services obtenue, cliquez sur le service de votre choix, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66c3d-115">L’outil de configuration Response Group s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="66c3d-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="66c3d-116">Vous pouvez également ouvrir l’outil de configuration Response Group directement à partir d’un navigateur Web en tapant l’URL suivante : <STRONG>https://</STRONG>&lt;webpoolfqdn représente&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="66c3d-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="66c3d-117">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="66c3d-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="66c3d-118">Sous **Créer un flux de travail**, à côté de **Interactif**, cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-118">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="66c3d-119">Sous **Gérer un flux de travail existant**, recherchez le flux de travail que vous souhaitez modifier, puis sous **Action**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="66c3d-120">Si vous n’êtes pas prêt et que les utilisateurs ne peuvent pas encore commencer à appeler le flux de travail, décochez la case **Activer le flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-120">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66c3d-p105">Si vous devez créer un flux de travail géré, sélectionnez <STRONG>Activer le flux de travail</STRONG>. Une fois le flux de travail géré actif enregistré, vous pouvez ensuite le modifier et le désactiver.</span><span class="sxs-lookup"><span data-stu-id="66c3d-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="66c3d-123">Pour autoriser les utilisateurs fédérés à appeler le groupe, activez la case à cocher **Activer pour la fédération**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="66c3d-124">Vous devez également disposer d’une stratégie d’accès externe qui s’applique à l’application Response Group configurée pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="66c3d-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66c3d-125">La stratégie d’accès externe globale s’applique à l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="66c3d-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="66c3d-126">Vous pouvez configurer la stratégie globale pour la Fédération Response Group à l’aide du panneau de configuration Lync Server ou à l’aide de la cmdlet <STRONG>Set-CsExternalAccessPolicy</STRONG> pour définir le paramètre EnableOutsideAccess sur true.</span><span class="sxs-lookup"><span data-stu-id="66c3d-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="66c3d-127">Gardez à l’esprit que les paramètres de stratégie globale s’appliquent à tous les utilisateurs sauf s’ils se voient affectés un site ou une stratégie utilisateur.</span><span class="sxs-lookup"><span data-stu-id="66c3d-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="66c3d-128">Par conséquent, avant de modifier ce paramètre pour les groupes Response Group, assurez-vous que le paramètre de fédération satisfait les exigences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="66c3d-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="66c3d-129">Pour plus d’informations sur l’application des stratégies aux utilisateurs, consultez la rubrique <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gestion de la stratégie d’accès externe dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="66c3d-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="66c3d-130">Pour plus d’informations sur le paramètre de Fédération, voir <STRONG>Set-CsExternalAccessPolicy</STRONG> dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="66c3d-130">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66c3d-131">Les utilisateurs hébergés dans Lync Online ne peuvent pas passer d’appels à des groupes Response Group qui sont hébergés dans un déploiement local.</span><span class="sxs-lookup"><span data-stu-id="66c3d-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="66c3d-132">Cela est vrai dans les déploiements hybrides et dans les cas où un déploiement sur site est fédéré avec un déploiement Lync Online.</span><span class="sxs-lookup"><span data-stu-id="66c3d-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="66c3d-133">Pour masquer l’identité des agents pendant les appels, activez la case à cocher **Activer l’anonymat de l’agent**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66c3d-134">Les appels anonymes ne peuvent pas démarrer avec la messagerie instantanée ou la vidéo, mais l’agent ou l’appelant peut ajouter la messagerie instantanée et la vidéo une fois que l’appel a commencé.</span><span class="sxs-lookup"><span data-stu-id="66c3d-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="66c3d-135">Un agent anonyme peut aussi mettre des appels en attente, transférer des appels (transferts invisibles et consultatifs), mais aussi parquer et récupérer des appels.</span><span class="sxs-lookup"><span data-stu-id="66c3d-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="66c3d-136">Les appels anonymes ne prennent pas en charge la conférence, le partage d’application, le partage du Bureau, le transfert de fichiers, le tableau blanc, la collaboration de données et l’enregistrement d’appel.</span><span class="sxs-lookup"><span data-stu-id="66c3d-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="66c3d-137">Les agents utilisant le plug-in Lync VDI peuvent recevoir des appels entrants de manière anonyme, mais ils ne peuvent pas passer des appels sortants de manière anonyme.</span><span class="sxs-lookup"><span data-stu-id="66c3d-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="66c3d-138">Sous **Entrez l’adresse du groupe qui recevra les appels**, cliquez sur l’adresse URI (Uniform Resource Identifier) du domaine SIP principal du groupe qui doit répondre aux appels pour le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="66c3d-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="66c3d-139">Dans **Nom d’affichage**, tapez le nom que vous souhaitez voir s’afficher pour le flux de travail (par exemple, Sales IVR Response Group).</span><span class="sxs-lookup"><span data-stu-id="66c3d-139">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66c3d-140">N’incluez pas les&lt;caractères « »&gt;ou « » dans le nom d’affichage.</span><span class="sxs-lookup"><span data-stu-id="66c3d-140">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="66c3d-141">N’utilisez pas les noms d’affichage suivants, car ils sont réservés : RGS Presence Watcher ou Service d’annonce.</span><span class="sxs-lookup"><span data-stu-id="66c3d-141">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="66c3d-142">Dans **Numéro de téléphone**, tapez L’URI de ligne pour le groupe Response Group (par exemple, +14255550165).</span><span class="sxs-lookup"><span data-stu-id="66c3d-142">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="66c3d-143">Dans **Numéro affiché**, tapez le numéro tel qu’il doit apparaître pour le groupe Response Group (par exemple, +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="66c3d-143">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="66c3d-144">Module Dans **Description**, tapez la description du flux de travail que vous souhaitez voir apparaître sur la carte de visite dans le client Lync.</span><span class="sxs-lookup"><span data-stu-id="66c3d-144">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="66c3d-145">Dans **Type de flux de travail**, sélectionnez **Géré** si ce flux de travail doit être géré par un gestionnaire Response Group.</span><span class="sxs-lookup"><span data-stu-id="66c3d-145">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="66c3d-146">Pour affecter des responsables de groupes Response Group au flux de travail, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="66c3d-146">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="66c3d-147">Tapez l’URI SIP d’un gestionnaire pour ce flux de travail, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-147">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="66c3d-148">Tapez l’URI SIP des autres gestionnaires à ajouter au flux de travail, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-148">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="66c3d-p112">Tout utilisateur désigné comme responsable d’un groupe Response group doit avoir le rôle CsResponseGroupManager qui lui est assigné. Dans le cas contraire, il ne peut pas gérer de groupe Response group.</span><span class="sxs-lookup"><span data-stu-id="66c3d-p112">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="66c3d-151">Sous **Étape 2 Sélectionner une langue**, cliquez sur la langue à utiliser pour la reconnaissance vocale et la synthèse vocale.</span><span class="sxs-lookup"><span data-stu-id="66c3d-151">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="66c3d-152">Si vous souhaitez configurer un message de bienvenue, sous **Étape 3 Configurer un message de bienvenue**, activez la case à cocher **Lisez un message de bienvenue**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="66c3d-152">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="66c3d-153">Pour entrer le message de bienvenue sous forme de texte converti en message vocal pour les appelants, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message de bienvenue dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="66c3d-153">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="66c3d-p113">N’incluez pas de balises HTML dans le texte que vous entrez. Sinon, vous recevrez un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="66c3d-p113">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="66c3d-p114">Pour utiliser un enregistrement de fichier Wave ou Windows Media Audio pour le message de bienvenue, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier audio que vous souhaitez utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="66c3d-p114">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="66c3d-160">Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères.</span><span class="sxs-lookup"><span data-stu-id="66c3d-160">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="66c3d-161">Pour plus d’informations sur les formats de fichiers pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="66c3d-161">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="66c3d-162">Sous **Étape 4 Spécifier vos heures d’ouverture**, dans la zone **Votre fuseau horaire**, cliquez sur le fuseau horaire du workflow.</span><span class="sxs-lookup"><span data-stu-id="66c3d-162">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66c3d-p116">Il s’agit du fuseau horaire des appelants et des agents du flux de travail. Il sert à calculer les heures d’ouverture et de fermeture. Par exemple, si le flux de travail est configuré pour utiliser le fuseau horaire Est de l’Amérique du Nord et que l’ouverture et la fermeture du flux sont planifiées respectivement pour 7 heures et 23 heures, il s’agit de l’heure d’ouverture 7:00 Est et de l’heure de fermeture 11:00:00 Est. (Vous devez entrer les heures au format 24 heures.)</span><span class="sxs-lookup"><span data-stu-id="66c3d-p116">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="66c3d-168">Sélectionnez le type d’heures d’ouverture que vous souhaitez utiliser en effectuant l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="66c3d-168">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="66c3d-169">Pour utiliser un planning prédéfini d’heures d’ouverture, cliquez sur **Utiliser un planning prédéfini**, puis sélectionnez le planning souhaité dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="66c3d-169">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="66c3d-170">Vous devez avoir défini précédemment au moins un planning prédéfini pour pouvoir sélectionner cette option.</span><span class="sxs-lookup"><span data-stu-id="66c3d-170">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="66c3d-171">Vous pouvez spécifier des plannings prédéfinis à l’aide de l’applet de commande <STRONG>New-CsRgsHoursOfBusiness</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="66c3d-171">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="66c3d-172">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-optional-define-response-group-business-hours.md">(facultatif) define Response Group Business hours in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="66c3d-172">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="66c3d-173">Lorsque vous sélectionnez un planning prédéfini, les champs <STRONG>Jour</STRONG>, <STRONG>Ouverture</STRONG> et <STRONG>Fermeture</STRONG> sont automatiquement renseignés avec les jours et les heures pendant lesquels le groupe Response Group est disponible.</span><span class="sxs-lookup"><span data-stu-id="66c3d-173">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="66c3d-174">Pour utiliser un planning personnalisé qui s’applique uniquement à ce workflow, cliquez sur **Utiliser un planning personnalisé**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-174">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="66c3d-175">Si vous créez un planning personnalisé pour ce workflow, activez les cases à cocher correspondant aux jours de la semaine pendant lesquels le groupe Response Group est disponible.</span><span class="sxs-lookup"><span data-stu-id="66c3d-175">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="66c3d-176">Si vous créez un planning personnalisé, tapez les heures **Ouverture** et **Fermeture** pendant lesquelles le groupe Response Group est disponible.</span><span class="sxs-lookup"><span data-stu-id="66c3d-176">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66c3d-p118">Les heures <STRONG>Ouverture</STRONG> et <STRONG>Fermeture</STRONG> doivent être au format 24 heures. Par exemple, si votre bureau est ouvert de 9 heures à 17 heures et ferme à midi pour le déjeuner, les heures d’ouverture sont spécifiées comme suit : <STRONG>Ouverture</STRONG> 9:00, <STRONG>Fermeture</STRONG> 12:00, <STRONG>Ouverture</STRONG> 13:00 et <STRONG>Fermeture</STRONG> 17:00.</span><span class="sxs-lookup"><span data-stu-id="66c3d-p118">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="66c3d-179">Si vous souhaitez que la lecture d’un message se déclenche lorsque le bureau est fermé, activez la case à cocher **Lisez un message lorsque le service Response Group est en dehors des heures d’ouverture**, puis spécifiez le message à lire en effectuant l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="66c3d-179">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="66c3d-180">Pour entrer le message sous forme de texte converti en message vocal pour l’appelant, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="66c3d-180">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="66c3d-p119">N’incluez pas de balises HTML dans le texte que vous entrez. Sinon, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="66c3d-p119">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="66c3d-p120">Pour utiliser un enregistrement de fichier audio pour le message, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier que vous souhaitez utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="66c3d-p120">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="66c3d-187">Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères.</span><span class="sxs-lookup"><span data-stu-id="66c3d-187">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="66c3d-188">Pour plus d’informations sur les formats de fichiers pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="66c3d-188">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="66c3d-189">Spécifiez comment gérer les appels après la lecture du message (si un message est configuré) :</span><span class="sxs-lookup"><span data-stu-id="66c3d-189">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="66c3d-190">Pour déconnecter l’appel, cliquez sur **Déconnecter l’appel**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-190">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="66c3d-191">Pour transférer l’appel vers la messagerie vocale, cliquez sur **Transférer à la messagerie vocale**, puis tapez l’adresse de la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="66c3d-191">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="66c3d-192">Le format de l’adresse de messagerie vocale \<est\>@\<NomUtilisateur\> nom_domaine (par exemple, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="66c3d-192">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="66c3d-193">Pour transférer l’appel vers un autre utilisateur, cliquez sur **Transférer à l’URI SIP**, puis tapez l’adresse de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="66c3d-193">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="66c3d-194">Le format de l’adresse de l' \<utilisateur\>@\<est\>username nom_domaine.</span><span class="sxs-lookup"><span data-stu-id="66c3d-194">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="66c3d-195">Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **Transférer au numéro de téléphone**, puis tapez le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="66c3d-195">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="66c3d-196">Le format du numéro de téléphone est \<le\>@\<numéro\> NomDomaine (par exemple, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="66c3d-196">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="66c3d-197">Le nom de domaine est utilisé pour acheminer l’appelant vers la destination appropriée.</span><span class="sxs-lookup"><span data-stu-id="66c3d-197">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="66c3d-198">Sous **Étape 5 Spécifier vos congés**, activez les cases à cocher correspondant à une ou plusieurs périodes de congés définissant les jours où le groupe Response Group est fermé.</span><span class="sxs-lookup"><span data-stu-id="66c3d-198">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66c3d-199">Vous devez définir les congés et les périodes de congé avant de configurer le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="66c3d-199">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="66c3d-200">Utilisez les applets de commande <STRONG>New-CsRgsHoliday</STRONG> et <STRONG>New-CsRgsHolidaySet</STRONG> pour créer des congés et des périodes de congé.</span><span class="sxs-lookup"><span data-stu-id="66c3d-200">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="66c3d-201">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(optional) define Response Group vacances sets in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="66c3d-201">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="66c3d-202">Si vous souhaitez que la lecture d’un message se déclenche pendant les congés, activez la case à cocher **Lisez un message pendant les congés**, puis spécifiez le message à lire en effectuant l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="66c3d-202">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="66c3d-203">Pour entrer le message sous forme de texte converti en message vocal pour l’appelant, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="66c3d-203">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="66c3d-p126">N’incluez pas de balises HTML dans le texte que vous entrez. Sinon, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="66c3d-p126">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="66c3d-p127">Pour utiliser un enregistrement de fichier audio pour le message, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier que vous souhaitez utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="66c3d-p127">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="66c3d-210">Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères.</span><span class="sxs-lookup"><span data-stu-id="66c3d-210">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="66c3d-211">Pour plus d’informations sur les formats de fichiers audio pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="66c3d-211">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="66c3d-212">Spécifiez comment gérer les appels après la lecture du message (si un message est configuré) :</span><span class="sxs-lookup"><span data-stu-id="66c3d-212">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="66c3d-213">Pour déconnecter l’appel, cliquez sur **Déconnecter l’appel**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-213">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="66c3d-214">Pour transférer l’appel vers la messagerie vocale, cliquez sur **Transférer à la messagerie vocale**, puis tapez l’adresse de la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="66c3d-214">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="66c3d-215">Le format de l’adresse de messagerie vocale \<est\>@\<NomUtilisateur\> nom_domaine (par exemple, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="66c3d-215">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="66c3d-216">Pour transférer l’appel vers un autre utilisateur, cliquez sur **Transférer à l’URI SIP**, puis tapez l’adresse de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="66c3d-216">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="66c3d-217">Le format de l’adresse de l' \<utilisateur\>@\<est\>username nom_domaine.</span><span class="sxs-lookup"><span data-stu-id="66c3d-217">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="66c3d-218">Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **Transférer au numéro de téléphone**, puis tapez le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="66c3d-218">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="66c3d-219">Le format du numéro de téléphone est \<le\>@\<numéro\> NomDomaine (par exemple, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="66c3d-219">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="66c3d-220">Le nom de domaine est utilisé pour acheminer l’appelant vers la destination appropriée.</span><span class="sxs-lookup"><span data-stu-id="66c3d-220">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="66c3d-221">Sous **Étape 6 Configurer une attente musicale**, choisissez ce que les appelants entendront pendant l’attente d’un agent. Pour cela, procédez de l’une des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="66c3d-221">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="66c3d-222">Pour utiliser l’enregistrement d’attente musicale par défaut, cliquez sur **Utiliser la valeur par défaut**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-222">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="66c3d-p132">Pour utiliser un enregistrement de fichier audio pour l’attente musicale, cliquez sur **Sélectionner un fichier de musique**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un fichier de musique**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier que vous souhaitez utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="66c3d-p132">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="66c3d-227">Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères.</span><span class="sxs-lookup"><span data-stu-id="66c3d-227">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="66c3d-228">Pour plus d’informations sur les formats de fichiers pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="66c3d-228">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="66c3d-229">Sous **Étape 7 Configurer la réponse vocale interactive**, dans l’en-tête **L’utilisateur entendra le texte ou message enregistré suivant**, spécifiez comme suit la question à poser aux appelants :</span><span class="sxs-lookup"><span data-stu-id="66c3d-229">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="66c3d-230">Pour entrer la question au format texte, cliquez sur **Utiliser la synthèse vocale**, puis tapez la question dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="66c3d-230">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="66c3d-p134">N’incluez pas de balises HTML dans le texte que vous entrez. Si vous incluez des balises HTML, vous recevrez un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="66c3d-p134">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="66c3d-233">Le moteur de synthèse vocale traduit le symbole « # » par le mot « numéro ».</span><span class="sxs-lookup"><span data-stu-id="66c3d-233">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="66c3d-234">Pour faire référence à la touche #, utilisez le nom de celle-ci au lieu de son symbole dans votre message d’invite.</span><span class="sxs-lookup"><span data-stu-id="66c3d-234">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="66c3d-235">Par exemple, « Pour être mis en relation avec le service commercial, appuyez sur la touche dièse ».</span><span class="sxs-lookup"><span data-stu-id="66c3d-235">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="66c3d-p136">Pour utiliser un fichier audio préenregistré contenant la question, cliquez sur **Sélectionner un enregistrement**, puis cliquez sur le lien **un enregistrement** pour télécharger le fichier. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier audio, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier, puis tapez éventuellement la question dans la zone de texte (la question, ainsi que la réponse de l’appelant seront transférées à l’agent qui répond).</span><span class="sxs-lookup"><span data-stu-id="66c3d-p136">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file. In the new browser window, click **Browse**, select the audio file, and then click **Open**. Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="66c3d-239">Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères.</span><span class="sxs-lookup"><span data-stu-id="66c3d-239">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="66c3d-240">Pour plus d’informations sur les formats de fichiers pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="66c3d-240">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="66c3d-241">Sous **Réponse 1**, procédez comme suit pour spécifier la première réponse possible à la question :</span><span class="sxs-lookup"><span data-stu-id="66c3d-241">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="66c3d-p138">N’incluez pas de guillemets (") dans les réponses vocales. Les guillemets entraînent l’échec de la réponse vocale interactive (IVR).</span><span class="sxs-lookup"><span data-stu-id="66c3d-p138">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66c3d-244">Vous pouvez choisir d’autoriser les appelants à répondre via une réponse vocale et/ou le clavier alphanumérique.</span><span class="sxs-lookup"><span data-stu-id="66c3d-244">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="66c3d-245">Si vous souhaitez permettre à l’appelant de répondre à l’aide d’une réponse vocale, entrez la réponse dans **Entrer une réponse vocale**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-245">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="66c3d-246">Si vous souhaitez permettre à l’appelant de répondre en appuyant sur une touche du pavé numérique, dans **Chiffre**, cliquez sur le chiffre du pavé numérique.</span><span class="sxs-lookup"><span data-stu-id="66c3d-246">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="66c3d-247">Spécifiez si l’appelant doit être acheminé vers une file d’attente ou si une autre question doit être posée. Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="66c3d-247">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="66c3d-248">Pour acheminer l’appelant vers une file d’attente, cliquez sur **Envoyer vers une file d’attente** et, dans **Sélectionner une file d’attente**, cliquez sur la file d’attente que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="66c3d-248">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="66c3d-p139">Pour poser une autre question, cliquez sur **Poser une autre question**, puis cliquez sur **Utiliser la synthèse vocale** et tapez la question, ou cliquez sur **Sélectionner un enregistrement**. Utilisez les regroupements de réponses de cette section pour spécifier jusqu’à quatre réponses possibles à la question supplémentaire, ainsi que la file d’attente à utiliser pour chaque réponse. Pour spécifier une troisième ou quatrième réponse possible, cochez la case **Réponse 3** ou **Réponse 4**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-p139">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="66c3d-p140">Spécifiez jusqu’à trois autres réponses possibles à la question d’origine en répétant les étapes 28 et 29, pour indiquer les réponses possibles et l’action à effectuer pour chaque réponse. Pour spécifier une troisième ou quatrième réponse possible, cochez la case **Réponse 3** ou **Réponse 4**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-p140">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="66c3d-254">Cliquez sur **Déployer**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-254">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="66c3d-255">Pour utiliser Windows PowerShell pour créer ou modifier un flux de travail interactif</span><span class="sxs-lookup"><span data-stu-id="66c3d-255">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="66c3d-256">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="66c3d-256">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="66c3d-257">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="66c3d-257">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="66c3d-p141">Déterminez le nom du service Response Group et affectez-le à une variable. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="66c3d-p141">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="66c3d-p142">Un flux de travail interactif nécessite au moins deux files d’attente et plusieurs groupes d’agents. Créez tout d’abord les groupes d’agents. Exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="66c3d-p142">An interactive workflow requires two or more queues and two or more agent groups. First, create the agent groups. Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="66c3d-p143">Créez des files d’attente. Exécutez :</span><span class="sxs-lookup"><span data-stu-id="66c3d-p143">Create the queues. Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="66c3d-p144">Créez la première invite Response group. Exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="66c3d-p144">Create the first response group prompt. Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="66c3d-p145">Créez ensuite l’action à effectuer après l’invite. Exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="66c3d-p145">Then create the action to be performed after the prompt. Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="66c3d-p146">Créez la première réponse Response group. Exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="66c3d-p146">Create the first response group answer. Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="66c3d-p147">Créez maintenant les deuxièmes invite, action d’appel et réponse. Créez d’abord l’invite. Exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="66c3d-p147">Now create the second prompt, call action, and answer. First create the prompt. Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="66c3d-p148">Créez la deuxième action d’appel. Exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="66c3d-p148">Create the second call action. Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="66c3d-p149">Créez la seconde réponse Response group. Exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="66c3d-p149">Create the second response group answer. Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="66c3d-p150">Créez l’invite de niveau supérieur. Exécutez :</span><span class="sxs-lookup"><span data-stu-id="66c3d-p150">Create the top-level prompt. Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="66c3d-p151">Créez la question de niveau supérieur. Exécutez :</span><span class="sxs-lookup"><span data-stu-id="66c3d-p151">Create the top-level question. Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="66c3d-p152">Créez maintenant le flux de travail. Exécutez :</span><span class="sxs-lookup"><span data-stu-id="66c3d-p152">Now create the workflow. Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66c3d-p153">Tous les utilisateurs désignés comme responsables d’un groupe Response group doivent avoir le rôle CsResponseGroupManager qui leur est assigné. Dans le cas contraire, ils ne peuvent pas gérer de groupe Response group.</span><span class="sxs-lookup"><span data-stu-id="66c3d-p153">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

