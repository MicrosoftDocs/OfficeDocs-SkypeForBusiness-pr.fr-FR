---
title: Gérer les applications approuvées
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Une application approuvée est une application basée sur le Kit de développement Microsoft Unified Communications Managed API (UCMA) 3.0 Core approuvé par Skype pour Business Server.
ms.openlocfilehash: b4bad58d93ca231a9405734dd148cee675c5d1ea
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222890"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="2c459-103">Gérer les applications approuvées dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="2c459-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="2c459-104">Une *application approuvée* est une application basée sur le Kit de développement Microsoft Unified Communications Managed API (UCMA) 3.0 Core approuvé par Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="2c459-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="2c459-105">Pour plus d’informations sur les applications UCMA, consultez la rubrique « Unified Communications gérées API 3.0 Core Documentation du kit SDK » http://go.microsoft.com/fwlink/p/?linkId=210320.</span><span class="sxs-lookup"><span data-stu-id="2c459-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="2c459-106">Pour publier avec succès, activer ou désactiver une topologie lors de l’ajout ou suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="2c459-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="2c459-107">Utilisez cet article pour apprendre à configurer un nouveau serveur d’applications approuvées, afficher la liste des applications approuvées et d’afficher des informations d’application approuvée.</span><span class="sxs-lookup"><span data-stu-id="2c459-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="2c459-108">Configurer un nouveau serveur d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="2c459-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="2c459-109">Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2c459-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="2c459-110">Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour le Générateur de topologie Business Server**.</span><span class="sxs-lookup"><span data-stu-id="2c459-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="2c459-111">Sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c459-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="2c459-112">Dans la boîte de dialogue **Enregistrer la topologie sous** , cliquez sur le fichier du Générateur de topologie que vous souhaitez utiliser, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2c459-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="2c459-113">Dans le volet gauche, cliquez sur **serveurs d’applications approuvées**, puis cliquez sur **Nouveau Pool d’applications approuvées**.</span><span class="sxs-lookup"><span data-stu-id="2c459-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="2c459-114">Entrez le **Nom complet du Pool** du pool d’applications approuvées, sélectionnez s’il sera un serveur unique ou plusieurs serveurs et puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="2c459-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="2c459-115">Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le Skype pour Business Server un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="2c459-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="2c459-116">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="2c459-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="2c459-117">Sélectionnez le nœud supérieur **Skype pour Business Server**, puis, dans le menu **Actions** , cliquez sur **Publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="2c459-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="2c459-118">Le **Pool d’applications approuvées** doivent créé avec succès et associé au pool frontal correct.</span><span class="sxs-lookup"><span data-stu-id="2c459-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="2c459-119">Afficher la liste des applications approuvées</span><span class="sxs-lookup"><span data-stu-id="2c459-119">View a list of trusted applications</span></span>

<span data-ttu-id="2c459-120">Vous pouvez utiliser la Skype pour Business Server Control Panel pour afficher la liste des applications approuvées que vous avez déployé dans votre Skype pour un environnement Business Server.</span><span class="sxs-lookup"><span data-stu-id="2c459-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="2c459-121">Une application approuvée est une application basée sur le Kit de développement Microsoft Unified Communications Managed API (UCMA) 3.0 Core approuvé par Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="2c459-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="2c459-122">Cette relation d’approbation est résumée dans la liste suivante :</span><span class="sxs-lookup"><span data-stu-id="2c459-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="2c459-123">Les applications approuvées ne requiert pas l’authentification par Skype Business Server.</span><span class="sxs-lookup"><span data-stu-id="2c459-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="2c459-124">Les applications approuvées ne sont pas limitées par Skype pour Business Server pour les transactions SIP, les connexions ou sortant voix sur IP (VoIP) appels.</span><span class="sxs-lookup"><span data-stu-id="2c459-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="2c459-125">Les applications approuvées peuvent emprunter l’identité d’un utilisateur et participer à des conférences sans apparaître dans les listes.</span><span class="sxs-lookup"><span data-stu-id="2c459-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="2c459-126">Les applications approuvées sont hautement disponibles et résistantes.</span><span class="sxs-lookup"><span data-stu-id="2c459-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="2c459-127">Dans Skype pour le panneau de configuration serveur Business, vous pouvez voir le nom des applications, le pool dans lequel elles s’exécutent et le port qu’elles utilisent.</span><span class="sxs-lookup"><span data-stu-id="2c459-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="2c459-128">Pour afficher la liste des applications approuvées</span><span class="sxs-lookup"><span data-stu-id="2c459-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="2c459-129">À partir d’un compte d’utilisateur auquel est affecté un rôle d’administrateur CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="2c459-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="2c459-130">Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Skype pour Business Server, voir [contrôle d’accès basé sur un rôle (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="2c459-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="2c459-131">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="2c459-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="2c459-132">Dans la barre de navigation de gauche, cliquez sur **la topologie**, puis cliquez sur **Application approuvée**.</span><span class="sxs-lookup"><span data-stu-id="2c459-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="2c459-133">Dans la page **Application approuvée** , cliquez sur un en-tête de colonne pour trier les applications, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2c459-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="2c459-134">Afficher les informations d’application approuvée</span><span class="sxs-lookup"><span data-stu-id="2c459-134">View trusted application information</span></span>

<span data-ttu-id="2c459-135">Vous pouvez afficher des informations sur les applications approuvées à l’aide de Windows PowerShell et l’applet de commande **Get-CsTrustedApplication** .</span><span class="sxs-lookup"><span data-stu-id="2c459-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="2c459-136">Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c459-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="2c459-137">Pour afficher les applications approuvées</span><span class="sxs-lookup"><span data-stu-id="2c459-137">To view trusted applications</span></span>

<span data-ttu-id="2c459-138">Pour afficher toutes les applications approuvées, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="2c459-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="2c459-139">Cette commande retourne des informations semblables à ce qui suit pour chaque application approuvée :</span><span class="sxs-lookup"><span data-stu-id="2c459-139">This command returns information similar to the following for each trusted application:</span></span>
    
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
    
   <span data-ttu-id="2c459-140">Pour plus d’informations, voir [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="2c459-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>