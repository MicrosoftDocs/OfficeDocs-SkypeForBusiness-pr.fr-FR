---
title: 'Lync Server 2013 : Activation des utilisateurs Lync pour le contrôle d’appel distant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6eae16d6dae46bab4f6cf745bc2e2a827eabcb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="f993f-102">Activation des utilisateurs Lync pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f993f-102">Enable Lync users for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f993f-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f993f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f993f-104">Vous pouvez configurer les utilisateurs de Lync pour le contrôle d’appel distant à l’aide de stratégies d’approvisionnement intrabande basées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="f993f-104">You can configure Lync users for remote call control by using in-band provisioning policies that are server-based.</span></span> <span data-ttu-id="f993f-105">Vous pouvez gérer les paramètres de mise en service intrabande à l’aide du panneau de configuration de Lync Server ou de l’interface de ligne de commande de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f993f-105">You can manage in-band provisioning settings by using Lync Server Control Panel or the Lync Server Management Shell command-line interface.</span></span> <span data-ttu-id="f993f-106">Ces outils remplacent le composant logiciel enfichable WMI (Windows Management Instrumentation) utilisé pour gérer les paramètres de stratégie de groupe dans les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="f993f-106">These tools replace the Windows Management Instrumentation (WMI) snap-in that was used to manage Group Policy settings in earlier releases.</span></span>

<span data-ttu-id="f993f-107">Si vous préférez permettre aux utilisateurs de configurer leur propre paramètre de contrôle d’appel distant dans Lync, vous pouvez configurer les paramètres de contrôle des appels distants pour les utilisateurs sur le serveur sans spécifier les valeurs **URI de ligne** et URI de **ligne** .</span><span class="sxs-lookup"><span data-stu-id="f993f-107">If you prefer to let users to configure their own remote call control settings in Lync, you can configure remote call control settings for users on the server without specifying **Line Server URI** and **Line URI** values.</span></span> <span data-ttu-id="f993f-108">Assurez-vous de communiquer les \*\*\*\* valeurs URI de ligne \*\*\*\* et URI de ligne appropriées à vos utilisateurs, puis fournissez aux utilisateurs les instructions de configuration de ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="f993f-108">Be sure that you communicate the appropriate **Line Server URI** and **Line URI** values to your users, and provide your users with the instructions to configure these settings.</span></span> <span data-ttu-id="f993f-109">Pour la procédure de configuration manuelle du contrôle d’appel distant dans Lync Server, voir la section «définir les options <http://go.microsoft.com/fwlink/p/?linkid=210132> et les numéros de téléphone» dans la documentation du client Lync sur le site Web Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="f993f-109">For the procedure to manually configure remote call control in Lync Server, see "Set Phones options and numbers" at <http://go.microsoft.com/fwlink/p/?linkid=210132> in the Lync client documentation on the Microsoft Office website.</span></span>

<span data-ttu-id="f993f-110">Si vous disposez d’un déploiement de 2007 Communications Server 2007 R2 ou Communications Server, les clients Communicator 2007 R2 et Office Communicator 2007 continuent d’utiliser une stratégie de groupe pendant la migration côte à côte.</span><span class="sxs-lookup"><span data-stu-id="f993f-110">If you have an existing Communications Server 2007 R2 or Communications Server 2007 deployment, Communicator 2007 R2 and Communicator 2007 clients will continue to use Group Policy during side-by-side migration.</span></span> <span data-ttu-id="f993f-111">Toutefois, si vous voulez que les paramètres de stratégie soient transférés aux clients Lync, vous devez configurer les paramètres de mise en service de Lync Server in-Band correspondants.</span><span class="sxs-lookup"><span data-stu-id="f993f-111">However, if you want policy settings to carry over to Lync clients, you need to configure the equivalent Lync Server in-band provisioning settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f993f-112">Pour permettre à un utilisateur d’utiliser le contrôle d’appel distant, vous devez fournir à l’utilisateur un URI de ligne et un URI de ligne serveur.</span><span class="sxs-lookup"><span data-stu-id="f993f-112">To enable a user for remote call control, you need to provide the user with both a Line URI and a Line Server URI.</span></span> <span data-ttu-id="f993f-113">Comme décrit dans <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">tâches de déploiement pour le contrôle d’appel distant dans Lync Server 2013</A>, vous devez être sûr d’utiliser la syntaxe requise par la passerelle pour ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="f993f-113">As described in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Deployment tasks for remote call control in Lync Server 2013</A>, you need to be sure to use the syntax that is required by the gateway for these settings.</span></span><BR><span data-ttu-id="f993f-114">Assurez-vous que le domaine dans l’URI ligne Server est le même que le domaine de destination que vous avez spécifié dans le paramètre MatchUri lorsque vous avez configuré l’itinéraire statique vers la passerelle.</span><span class="sxs-lookup"><span data-stu-id="f993f-114">Be sure that the domain in the Line Server URI is the same as the destination domain that you specified in the MatchUri parameter when you configured the static route to the gateway.</span></span><BR><span data-ttu-id="f993f-115">L’URI de ligne indique le numéro de téléphone attribué à l’utilisateur au format E. 164, avec le préfixe «TEL:» (par exemple, tel: + 14255550150).</span><span class="sxs-lookup"><span data-stu-id="f993f-115">The Line URI specifies the phone number assigned to the user in E.164 format, with the "TEL:" prefix (for example, tel:+14255550150).</span></span> <span data-ttu-id="f993f-116">Si vous voulez configurer un numéro de poste, le format est tel: + 14255550150; ext = 111.</span><span class="sxs-lookup"><span data-stu-id="f993f-116">If you want to configure an extension number, then the format is tel:+14255550150;ext=111.</span></span> <span data-ttu-id="f993f-117">Si vous avez précédemment configuré l’URI de ligne de l’utilisateur et que la valeur n’a pas changé, vous n’avez pas besoin de spécifier l’URI de ligne lorsque vous activez le contrôle d’appel distant de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f993f-117">If you previously configured the user’s Line URI and the value has not changed, you do not need to specify the Line URI when you enable the user for remote call control.</span></span>



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a><span data-ttu-id="f993f-118">Pour activer le contrôle d’appel distant pour les utilisateurs compatibles Lync à l’aide de Management Shell</span><span class="sxs-lookup"><span data-stu-id="f993f-118">To enable remote call control for Lync-enabled users by using Management Shell</span></span>

1.  <span data-ttu-id="f993f-119">Connectez-vous à un ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou en tant que rôle de contrôle d’accès basé sur le rôle auquel vous avez affecté l’applet de commande **Set-Csuser** .</span><span class="sxs-lookup"><span data-stu-id="f993f-119">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or as a role-based access control role to which you have assigned the **Set-CsUser** cmdlet.</span></span>

2.  <span data-ttu-id="f993f-120">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f993f-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f993f-121">Pour utiliser l’applet de commande **Set-Csuser** pour configurer le contrôle d’appel distant pour un utilisateur existant Lync, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="f993f-121">To use the **Set-CsUser** cmdlet to configure remote call control for an existing Lync-enabled user, do the following:</span></span>
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    <span data-ttu-id="f993f-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f993f-122">For example:</span></span>
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a><span data-ttu-id="f993f-123">Pour configurer les utilisateurs pour le contrôle d’appel distant à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f993f-123">To configure users for remote call control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f993f-124">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f993f-124">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f993f-125">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f993f-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f993f-126">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f993f-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f993f-127">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f993f-127">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f993f-128">Dans la boîte de dialogue **Rechercher des utilisateurs** , tapez tout (ou la première partie) du nom d’affichage, prénom, nom, nom du compte de comptes de sécurité (Sam), adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur que vous souhaitez, puis cliquez sur \*\* Recherchez\*\*.</span><span class="sxs-lookup"><span data-stu-id="f993f-128">In the **Search users** box, type all (or the first portion) of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="f993f-129">Dans la table, cliquez sur le compte d’utilisateur que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="f993f-129">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="f993f-130">Dans le menu **édition** , cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="f993f-130">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="f993f-131">Dans **téléphonie**, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="f993f-131">In **Telephony**, do one of the following:</span></span>
    
      - <span data-ttu-id="f993f-132">Pour activer le contrôle d’appel distant et permettre à l’utilisateur de contrôler son téléphone PBX à partir de Lync 2013 pour passer des appels audio et des appels de PC à téléphone, cliquez sur **contrôle d’appel distant**.</span><span class="sxs-lookup"><span data-stu-id="f993f-132">To enable remote call control to enable the user to control their private branch exchange (PBX) phone from Lync 2013 to make PC-to-PC audio calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="f993f-133">Dans **URI de ligne**, spécifiez le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f993f-133">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="f993f-134">Dans **URI Line Server**, spécifiez l’URI SIP de la passerelle SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="f993f-134">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>
    
      - <span data-ttu-id="f993f-135">Pour activer le contrôle d’appel distant, mais désactiver les appels audio de PC à PC et permettre uniquement à l’utilisateur de contrôler son téléphone PBX à partir de Lync 2013 pour passer des appels de PC à téléphone, cliquez sur **contrôle d’appel distant uniquement**.</span><span class="sxs-lookup"><span data-stu-id="f993f-135">To enable remote call control, but disable PC-to-PC audio calls, and to enable only the user to control their PBX phone from Lync 2013 to make PC-to-phone calls, click **Remote call control only**.</span></span> <span data-ttu-id="f993f-136">Dans **URI de ligne**, spécifiez le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f993f-136">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="f993f-137">Dans **URI Line Server**, spécifiez l’URI SIP de la passerelle SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="f993f-137">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>

8.  <span data-ttu-id="f993f-138">Lorsque vous avez terminé, cliquez sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="f993f-138">When you are finished, click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

