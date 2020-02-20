---
title: Gérer les applications approuvées
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Une application approuvée est une application basée sur Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK approuvé par Skype entreprise Server.
ms.openlocfilehash: c5c1a62440ebb98974cee5771c13cf0e5acc55c7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151224"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="7957d-103">Gérer les applications approuvées dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7957d-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="7957d-104">Une *application approuvée* est une application basée sur Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK approuvé par Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7957d-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="7957d-105">Pour plus d’informations sur les applications UCMA, voir «documentation du https://go.microsoft.com/fwlink/p/?linkId=210320Kit de développement logiciel (SDK) Unified Communications Managed API 3,0.</span><span class="sxs-lookup"><span data-stu-id="7957d-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at https://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="7957d-106">Pour publier, activer ou désactiver correctement une topologie lors de l’ajout ou de la suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="7957d-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="7957d-107">Cet article explique comment configurer un nouveau serveur d’applications approuvées, afficher la liste des applications approuvées et afficher les informations sur les applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="7957d-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="7957d-108">Configurer un nouveau serveur d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="7957d-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="7957d-109">Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7957d-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="7957d-110">Démarrez le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server**, puis sur **Générateur de topologie Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="7957d-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="7957d-111">Sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7957d-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="7957d-112">Dans la boîte de dialogue **enregistrer la topologie sous** , cliquez sur le fichier du générateur de topologies que vous souhaitez utiliser, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7957d-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="7957d-113">Dans le volet de gauche, cliquez avec le bouton droit sur **serveurs d’applications approuvées**, puis cliquez sur **nouveau pool d’applications approuvées**.</span><span class="sxs-lookup"><span data-stu-id="7957d-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="7957d-114">Entrez le **Nom de domaine complet (FQDN) du pool** de l’application approuvée, sélectionnez s’il s’agira d’un serveur unique ou d’un serveur multiple, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="7957d-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="7957d-115">Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7957d-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="7957d-116">Cliquez sur**Terminer**.</span><span class="sxs-lookup"><span data-stu-id="7957d-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="7957d-117">Sélectionnez le nœud supérieur **Skype entreprise Server**, puis, dans le menu **actions** , cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="7957d-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="7957d-118">Le **pool d’applications approuvées** doit avoir été créé avec succès et associé au pool frontal correct.</span><span class="sxs-lookup"><span data-stu-id="7957d-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="7957d-119">Afficher la liste des applications approuvées</span><span class="sxs-lookup"><span data-stu-id="7957d-119">View a list of trusted applications</span></span>

<span data-ttu-id="7957d-120">Vous pouvez utiliser le panneau de configuration de Skype entreprise Server pour afficher la liste des applications approuvées que vous avez déployées dans votre environnement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7957d-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="7957d-121">Une application approuvée est une application basée sur Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK approuvé par Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7957d-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="7957d-122">Cette relation d’approbation est résumée dans la liste suivante :</span><span class="sxs-lookup"><span data-stu-id="7957d-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="7957d-123">Les applications approuvées ne sont pas contestées pour l’authentification par Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7957d-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="7957d-124">Les applications approuvées ne sont pas limitées par Skype entreprise Server pour les transactions SIP, les connexions ou les appels VoIP (Voice over Internet Protocol) sortants.</span><span class="sxs-lookup"><span data-stu-id="7957d-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="7957d-125">Les applications approuvées peuvent emprunter l’identité de n’importe quel utilisateur et participer à des conférences sans apparaître dans les listes.</span><span class="sxs-lookup"><span data-stu-id="7957d-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="7957d-126">Les applications approuvées sont hautement disponibles et résilientes.</span><span class="sxs-lookup"><span data-stu-id="7957d-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="7957d-127">Dans le panneau de configuration de Skype entreprise Server, vous pouvez voir le nom des applications, le pool où elles s’exécutent, ainsi que le port qu’elles utilisent.</span><span class="sxs-lookup"><span data-stu-id="7957d-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="7957d-128">Pour afficher la liste des applications approuvées</span><span class="sxs-lookup"><span data-stu-id="7957d-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="7957d-129">Avec un compte d’utilisateur affecté au rôle CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="7957d-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="7957d-130">Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Skype entreprise Server, consultez la rubrique [contrôle d’accès basé sur un rôle (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="7957d-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="7957d-131">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7957d-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="7957d-132">Dans la barre de navigation de gauche, cliquez sur **topologie**, puis sur **application approuvée**.</span><span class="sxs-lookup"><span data-stu-id="7957d-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="7957d-133">Sur la page **application approuvée** , cliquez sur un en-tête de colonne pour trier les applications, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="7957d-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="7957d-134">Afficher les informations de l’application approuvée</span><span class="sxs-lookup"><span data-stu-id="7957d-134">View trusted application information</span></span>

<span data-ttu-id="7957d-135">Vous pouvez afficher des informations sur vos applications approuvées à l’aide de Windows PowerShell et de la cmdlet **Get-CsTrustedApplication** .</span><span class="sxs-lookup"><span data-stu-id="7957d-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="7957d-136">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7957d-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="7957d-137">Pour afficher les applications approuvées</span><span class="sxs-lookup"><span data-stu-id="7957d-137">To view trusted applications</span></span>

<span data-ttu-id="7957d-138">Pour afficher toutes vos applications approuvées, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="7957d-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="7957d-139">Cette commande retourne des informations identiques aux suivantes pour chaque application approuvée :</span><span class="sxs-lookup"><span data-stu-id="7957d-139">This command returns information similar to the following for each trusted application:</span></span>
    
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
    
   <span data-ttu-id="7957d-140">Pour plus d’informations, voir [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="7957d-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>
