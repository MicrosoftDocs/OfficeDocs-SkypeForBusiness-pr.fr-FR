---
title: Gérer les applications fiables
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Une application fiable est une application basée sur le SDK Microsoft Unified Communications Managed API (UCMA) 3.0 Core approuvé par Skype Entreprise Server.
ms.openlocfilehash: b99b1c989437e6f474a97463fc53d4179858346e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103160"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="3f68d-103">Gérer les applications de confiance dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="3f68d-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="3f68d-104">Une *application fiable* est une application basée sur le SDK Microsoft Unified Communications Managed API (UCMA) 3.0 Core approuvé par Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3f68d-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="3f68d-105">Pour plus d’informations sur les applications UCMA, voir « Documentation du SDK Unified Communications Managed API 3.0 Core » sur https://go.microsoft.com/fwlink/p/?linkId=210320 .</span><span class="sxs-lookup"><span data-stu-id="3f68d-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at https://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="3f68d-106">Pour publier, activer ou désactiver correctement une topologie lors de l’ajout ou de la suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="3f68d-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="3f68d-107">Utilisez cet article pour découvrir comment configurer un nouveau serveur d’applications approuvé, afficher une liste d’applications fiables et afficher des informations sur les applications de confiance.</span><span class="sxs-lookup"><span data-stu-id="3f68d-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="3f68d-108">Configurer un nouveau serveur d’applications fiables</span><span class="sxs-lookup"><span data-stu-id="3f68d-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="3f68d-109">Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3f68d-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="3f68d-110">Démarrez le Générateur de topologie : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **Server,** puis sur Générateur de topologie **Skype Entreprise Server.**</span><span class="sxs-lookup"><span data-stu-id="3f68d-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="3f68d-111">Sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f68d-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="3f68d-112">Dans la boîte de dialogue Enregistrer la topologie **sous,** cliquez sur le fichier du Générateur de topologie que vous souhaitez utiliser, puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="3f68d-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="3f68d-113">Dans le volet gauche, cliquez avec le bouton droit sur **Serveurs d’applications** de confiance, puis cliquez sur **Nouveau pool d’applications fiables.**</span><span class="sxs-lookup"><span data-stu-id="3f68d-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="3f68d-114">Entrez le **Nom de domaine complet (FQDN) du pool** de l’application approuvée, sélectionnez s’il s’agira d’un serveur unique ou d’un serveur multiple, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3f68d-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="3f68d-115">Dans la page **Sélectionner le saut suivant,** dans la liste, sélectionnez le pool frontal Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3f68d-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="3f68d-116">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="3f68d-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="3f68d-117">Sélectionnez le nœud supérieur **Skype Entreprise Server,** puis, dans le menu **Actions,** cliquez sur **Publier la topologie.**</span><span class="sxs-lookup"><span data-stu-id="3f68d-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="3f68d-118">Le **pool d’applications** fiables doit avoir été créé avec succès et associé au pool frontal correct.</span><span class="sxs-lookup"><span data-stu-id="3f68d-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="3f68d-119">Afficher une liste d’applications fiables</span><span class="sxs-lookup"><span data-stu-id="3f68d-119">View a list of trusted applications</span></span>

<span data-ttu-id="3f68d-120">Vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server pour afficher la liste des applications de confiance que vous avez déployées dans votre environnement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3f68d-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="3f68d-121">Une application fiable est une application basée sur le SDK Microsoft Unified Communications Managed API (UCMA) 3.0 Core approuvé par Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3f68d-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="3f68d-122">Cette relation d’confiance est résumée dans la liste suivante :</span><span class="sxs-lookup"><span data-stu-id="3f68d-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="3f68d-123">L’authentification par Skype Entreprise Server ne demande pas d’authentification aux applications fiables.</span><span class="sxs-lookup"><span data-stu-id="3f68d-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="3f68d-124">Les applications fiables ne sont pas limitées par Skype Entreprise Server pour les transactions SIP, les connexions ou les appels VoIP (Voice over Internet Protocol) sortants.</span><span class="sxs-lookup"><span data-stu-id="3f68d-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="3f68d-125">Les applications fiables peuvent usurper l’identité de n’importe quel utilisateur et participer à des conférences sans apparaître dans les listes.</span><span class="sxs-lookup"><span data-stu-id="3f68d-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="3f68d-126">Les applications fiables sont hautement disponibles et résilientes.</span><span class="sxs-lookup"><span data-stu-id="3f68d-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="3f68d-127">Dans le Panneau de contrôle Skype Entreprise Server, vous pouvez voir le nom des applications, le pool dans lequel elles s’exécutent et le port qu’elles utilisent.</span><span class="sxs-lookup"><span data-stu-id="3f68d-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="3f68d-128">Pour afficher une liste d’applications fiables</span><span class="sxs-lookup"><span data-stu-id="3f68d-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="3f68d-129">Avec un compte d’utilisateur affecté au rôle CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3f68d-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="3f68d-130">Pour plus d’informations sur les rôles d’administration prédéfincis disponibles dans Skype Entreprise Server, voir Contrôle d’accès basé sur un rôle [(RBAC).](../plan-your-deployment/security/role-based-access-control-rbac.md)</span><span class="sxs-lookup"><span data-stu-id="3f68d-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="3f68d-131">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3f68d-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="3f68d-132">Dans la barre de navigation de gauche, cliquez sur **Topologie,** puis sur **Application de confiance.**</span><span class="sxs-lookup"><span data-stu-id="3f68d-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="3f68d-133">Dans la page **Application de** confiance, cliquez sur un en-tête de colonne pour trier les applications, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3f68d-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="3f68d-134">Afficher les informations sur les applications fiables</span><span class="sxs-lookup"><span data-stu-id="3f68d-134">View trusted application information</span></span>

<span data-ttu-id="3f68d-135">Vous pouvez afficher des informations sur vos applications de confiance à l’aide Windows PowerShell et de l’cmdlet **Get-CsTrustedApplication.**</span><span class="sxs-lookup"><span data-stu-id="3f68d-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="3f68d-136">Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f68d-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="3f68d-137">Pour afficher les applications approuvées</span><span class="sxs-lookup"><span data-stu-id="3f68d-137">To view trusted applications</span></span>

<span data-ttu-id="3f68d-138">Pour afficher toutes vos applications de confiance, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="3f68d-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="3f68d-139">Cette commande retourne des informations identiques aux suivantes pour chaque application approuvée :</span><span class="sxs-lookup"><span data-stu-id="3f68d-139">This command returns information similar to the following for each trusted application:</span></span>
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   <span data-ttu-id="3f68d-140">Pour plus d’informations, voir [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="3f68d-140">For details, see [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).</span></span>