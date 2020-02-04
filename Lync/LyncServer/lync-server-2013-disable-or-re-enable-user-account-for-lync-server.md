---
title: 'Lync Server 2013 : désactiver ou réactiver un compte d’utilisateur pour Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aea86048fa29e9b6a21aa040093edff3f53ffe27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="dc2d7-102">Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc2d7-102">Disable or re-enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc2d7-103">_**Dernière modification de la rubrique :** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="dc2d7-103">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="dc2d7-104">Vous pouvez utiliser la procédure suivante pour désactiver un compte d’utilisateur déjà activé dans Lync Server 2013 sans perdre les paramètres de serveur Lync que vous avez configurés pour le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-104">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="dc2d7-105">Étant donné que vous ne perdez pas les paramètres de compte d’utilisateur de Lync Server, vous pouvez réactiver un compte d’utilisateur déjà activé sans avoir à reconfigurer le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-105">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="dc2d7-106">La désactivation d’un compte d’utilisateur dans Active Directory n' <STRONG>empêchera pas</STRONG> un utilisateur de se connecter ou d’utiliser Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-106">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="dc2d7-107">En effet, Lync utilise l’authentification par certificat qui rationalise le processus d’authentification, et ces certificats clients sont valides pour 180 jours.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-107">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="dc2d7-108">Si vous souhaitez désactiver les comptes Active Directory désactivés qui ont été activés pour Lync et avoir accès à Lync Server, vous devez utiliser l’applet de commande <STRONG>Disable-Csuser</STRONG> , ou utiliser le <STRONG>panneau de configuration de Lync Server</STRONG> comme prévu dans cet article.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-108">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="dc2d7-109">Lorsque l’utilisateur est désactivé dans Lync et que le magasin de gestion central a été répliqué dans l’environnement, les utilisateurs ne seront plus en mesure de se connecter.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-109">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="dc2d7-110">De plus, les utilisateurs connectés seront déconnectés.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-110">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="dc2d7-111">Pour désactiver ou réactiver un compte d’utilisateur déjà activé pour Lync Server</span><span class="sxs-lookup"><span data-stu-id="dc2d7-111">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="dc2d7-112">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc2d7-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dc2d7-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dc2d7-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dc2d7-115">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="dc2d7-116">Dans la boîte de dialogue **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, nom, nom du compte de comptes de sécurité (Sam), adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="dc2d7-117">Dans la table, cliquez sur le compte d’utilisateur que vous souhaitez désactiver ou réactiver.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-117">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="dc2d7-118">Dans le menu **action** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dc2d7-118">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="dc2d7-119">Pour désactiver temporairement le compte d’utilisateur pour Lync Server 2013, cliquez sur **désactiver temporairement pour Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-119">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="dc2d7-120">Pour activer le compte d’utilisateur pour Lync Server 2013, cliquez sur **réactiver pour Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-120">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="dc2d7-121">Utilisation de Windows PowerShell pour désactiver ou réactiver les comptes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="dc2d7-121">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="dc2d7-122">Pour désactiver temporairement les comptes d’utilisateurs, vous pouvez les réactiver ultérieurement à l’aide de l’applet de dialogue **Set-Csuser** .</span><span class="sxs-lookup"><span data-stu-id="dc2d7-122">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="dc2d7-123">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc2d7-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dc2d7-124">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="dc2d7-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="dc2d7-125">Pour désactiver un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="dc2d7-125">To disable a user account</span></span>

  - <span data-ttu-id="dc2d7-126">Pour désactiver temporairement un compte d’utilisateur, définissez la valeur de la propriété Enabled sur false ($False).</span><span class="sxs-lookup"><span data-stu-id="dc2d7-126">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="dc2d7-127">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="dc2d7-127">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="dc2d7-128">Pour réactiver un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="dc2d7-128">To re-enable a user account</span></span>

  - <span data-ttu-id="dc2d7-129">Pour réactiver un compte d’utilisateur désactivé, définissez la valeur de la propriété Enabled sur true ($True).</span><span class="sxs-lookup"><span data-stu-id="dc2d7-129">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="dc2d7-130">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="dc2d7-130">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="dc2d7-131">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-Csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="dc2d7-131">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dc2d7-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dc2d7-132">See Also</span></span>


[<span data-ttu-id="dc2d7-133">Ajouter et activer un compte d’utilisateur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc2d7-133">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="dc2d7-134">Activation et désactivation des utilisateurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc2d7-134">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

