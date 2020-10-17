---
title: 'Lync Server 2013 : création ou modification des paramètres de code confidentiel des conférences rendez-vous pour un site ou un groupe d’utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify dial-in conferencing PIN settings for a site or group of users
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48185326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad85e0ebd3005fb57d4c23b13874c37b36dbe128
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516871"
---
# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a><span data-ttu-id="fccba-102">Création ou modification des paramètres de code confidentiel des conférences rendez-vous dans Lync Server 2013 pour un site ou un groupe d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fccba-102">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fccba-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="fccba-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="fccba-104">Procédez comme suit pour créer ou modifier une stratégie de code confidentiel de conférence rendez-vous au niveau de l’utilisateur ou du site.</span><span class="sxs-lookup"><span data-stu-id="fccba-104">Follow these steps to create or modify a user-level or a site-level dial-in conferencing personal identification number (PIN) policy.</span></span> <span data-ttu-id="fccba-105">Pour plus d’informations sur la modification de la stratégie de code confidentiel globale, voir [modifier les paramètres de code confidentiel de conférence rendez-vous par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="fccba-105">For details about how to change the global PIN policy, see [Modify the default dial-in conferencing PIN settings in Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span></span>

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="fccba-106">Pour créer une stratégie de code confidentiel au niveau utilisateur ou site</span><span class="sxs-lookup"><span data-stu-id="fccba-106">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="fccba-107">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fccba-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="fccba-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fccba-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fccba-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fccba-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fccba-110">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="fccba-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="fccba-111">Dans la page **Stratégie de code confidentiel**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fccba-111">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="fccba-p103">Pour créer une stratégie au niveau utilisateur, cliquez sur **Stratégie de l’utilisateur**. Dans **Nouvelle stratégie de code confidentiel**, dans **Nom**, tapez un nom décrivant la stratégie.</span><span class="sxs-lookup"><span data-stu-id="fccba-p103">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
      - <span data-ttu-id="fccba-p104">Pour créer une stratégie au niveau site, cliquez sur **Stratégie du site**. Dans la zone de recherche **Sélectionner un site**, tapez entièrement ou partiellement le nom du site pour lequel vous voulez créer une stratégie. Dans la liste des sites, cliquez sur le site voulu, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fccba-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="fccba-117">Dans le champ **Description**, tapez la description de la stratégie de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="fccba-117">In the **Description** field, type a description of the PIN policy.</span></span>

6.  <span data-ttu-id="fccba-p105">Dans le champ **Longueur minimale du code confidentiel**, tapez ou sélectionnez la longueur minimale du code confidentiel que vous souhaitez autoriser. La longueur minimale par défaut est de cinq chiffres.</span><span class="sxs-lookup"><span data-stu-id="fccba-p105">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

7.  <span data-ttu-id="fccba-p106">Si vous voulez spécifier le nombre maximal de tentatives de connexion avant le verrouillage de l’utilisateur, activez la case à cocher **Spécifier le nombre maximal de tentatives de connexion**. Si vous ne sélectionnez pas cette option, le nombre maximal de tentatives est automatiquement déterminé en fonction de la longueur du code confidentiel. Par défaut, le nombre maximal de tentatives est automatiquement déterminé.</span><span class="sxs-lookup"><span data-stu-id="fccba-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

8.  <span data-ttu-id="fccba-123">Si vous avez activé la case à cocher **Spécifier le nombre maximal de tentatives de connexion**, dans **Nombre maximal de tentatives de connexion**, tapez ou sélectionnez le nombre maximal de tentatives de connexion que vous souhaitez autoriser.</span><span class="sxs-lookup"><span data-stu-id="fccba-123">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

9.  <span data-ttu-id="fccba-p107">Si vous voulez que les codes confidentiels expirent, activez la case à cocher **Activer l’expiration du code confidentiel**. Si vous ne sélectionnez pas cette option, les codes confidentiels n’expirent jamais. Par défaut, les codes confidentiels n’expirent jamais.</span><span class="sxs-lookup"><span data-stu-id="fccba-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

10. <span data-ttu-id="fccba-127">Si vous avez activé la case à cocher **Activer l’expiration du code confidentiel**, dans **Le code confidentiel expire au bout de (jours)**, tapez ou sélectionnez le nombre de jours après lequel les codes confidentiels expirent.</span><span class="sxs-lookup"><span data-stu-id="fccba-127">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

11. <span data-ttu-id="fccba-p108">Dans **Comptage de l’historique du code confidentiel**, tapez le nombre de codes confidentiels qu’un utilisateur doit créer avant qu’il ne puisse réutiliser un code. Par défaut, les utilisateurs peuvent réutiliser leur code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="fccba-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

12. <span data-ttu-id="fccba-p109">Pour autoriser les modèles courants de codes confidentiels, tels que les jeux de chiffres séquentiels et répétitifs, activez la case à cocher **Autoriser les modèles courants**. Si vous ne sélectionnez pas cette option, seuls les modèles complexes de chiffres sont autorisés. Par défaut, seuls les modèles complexes de chiffres sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="fccba-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="fccba-133">Nous vous recommandons de ne pas autoriser les modèles courants.</span><span class="sxs-lookup"><span data-stu-id="fccba-133">We recommend that you do not allow common patterns.</span></span>

    
    </div>

13. <span data-ttu-id="fccba-134">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="fccba-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a><span data-ttu-id="fccba-135">Pour modifier une stratégie de code confidentiel au niveau de l’utilisateur ou du site</span><span class="sxs-lookup"><span data-stu-id="fccba-135">To change a user or site PIN policy</span></span>

1.  <span data-ttu-id="fccba-136">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fccba-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="fccba-137">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fccba-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fccba-138">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fccba-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fccba-139">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="fccba-139">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="fccba-140">Dans la page **Stratégie de code confidentiel**, cliquez successivement sur la stratégie de code confidentiel à modifier, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="fccba-140">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="fccba-141">Dans **Modifier la stratégie de code confidentiel**, modifiez tous les paramètres de la stratégie (à l’exception de son nom qui ne peut être modifié).</span><span class="sxs-lookup"><span data-stu-id="fccba-141">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>

6.  <span data-ttu-id="fccba-142">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="fccba-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

