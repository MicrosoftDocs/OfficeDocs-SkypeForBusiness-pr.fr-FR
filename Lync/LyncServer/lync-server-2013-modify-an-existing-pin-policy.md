---
title: 'Lync Server 2013 : modifier une stratégie de code confidentiel existante'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify an existing PIN policy
ms:assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520993(v=OCS.15)
ms:contentKeyID: 48184143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27f5fcc560f302021effd90ce1b16cafb933ae03
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-an-existing-pin-policy-in-lync-server-2013"></a><span data-ttu-id="63879-102">Modifier une stratégie de code confidentiel existante dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63879-102">Modify an existing PIN policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63879-103">_**Dernière modification de la rubrique :** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="63879-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="63879-104">Vous pouvez utiliser l’onglet **stratégie de code confidentiel** pour fournir une authentification par code confidentiel aux utilisateurs qui se connectent à Lync 2013 avec des téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="63879-104">You can use the **PIN Policy** tab to provide personal identification number (PIN) authentication to users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="63879-105">Pour utiliser l’authentification par code confidentiel, assurez-vous que l’option **Activer l’authentification par code confidentiel** est sélectionnée dans les paramètres du service web.</span><span class="sxs-lookup"><span data-stu-id="63879-105">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="63879-106">Pour plus d’informations, consultez la rubrique [modifier les paramètres de configuration d’un service Web existant dans Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="63879-106">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="63879-107">Suivez ces étapes pour modifier une stratégie de code confidentiel au niveau du site ou de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="63879-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-modify-an-existing-pin-policy"></a><span data-ttu-id="63879-108">Pour modifier une stratégie de code confidentiel existante</span><span class="sxs-lookup"><span data-stu-id="63879-108">To modify an existing PIN policy</span></span>

1.  <span data-ttu-id="63879-109">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63879-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="63879-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="63879-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="63879-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="63879-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="63879-112">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="63879-112">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="63879-113">Dans la page **Stratégie de code confidentiel**, cliquez sur une stratégie, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="63879-113">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="63879-p103">Dans \*\*Modifier la stratégie de code confidentiel \*\*, dans **Longueur minimale du code confidentiel**, tapez ou sélectionnez la longueur minimale du code confidentiel que vous voulez autoriser. La longueur minimale par défaut est de cinq chiffres.</span><span class="sxs-lookup"><span data-stu-id="63879-p103">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

6.  <span data-ttu-id="63879-p104">Si vous voulez spécifier le nombre maximal de tentatives de connexion avant le verrouillage de l’utilisateur, activez la case à cocher **Spécifier le nombre maximal de tentatives de connexion**. Si vous ne sélectionnez pas cette option, le nombre maximal de tentatives est automatiquement déterminé en fonction de la longueur du code confidentiel. Par défaut, le nombre maximal de tentatives est automatiquement déterminé.</span><span class="sxs-lookup"><span data-stu-id="63879-p104">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

7.  <span data-ttu-id="63879-119">Si vous avez activé la case à cocher **Spécifier le nombre maximal de tentatives de connexion**, dans **Nombre maximal de tentatives de connexion**, tapez ou sélectionnez le nombre maximal de tentatives de connexion que vous souhaitez autoriser.</span><span class="sxs-lookup"><span data-stu-id="63879-119">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

8.  <span data-ttu-id="63879-p105">Si vous voulez que les codes confidentiels expirent, activez la case à cocher **Activer l’expiration du code confidentiel**. Si vous ne sélectionnez pas cette option, les codes confidentiels n’expirent jamais. Par défaut, les codes confidentiels n’expirent jamais.</span><span class="sxs-lookup"><span data-stu-id="63879-p105">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

9.  <span data-ttu-id="63879-123">Si vous avez activé la case à cocher **Activer l’expiration du code confidentiel**, dans **Le code confidentiel expire au bout de (jours)**, tapez ou sélectionnez le nombre de jours après lequel les codes confidentiels expirent.</span><span class="sxs-lookup"><span data-stu-id="63879-123">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

10. <span data-ttu-id="63879-p106">Dans **Comptage de l’historique du code confidentiel**, tapez le nombre de codes confidentiels qu’un utilisateur doit créer avant qu’il ne puisse réutiliser un code. Par défaut, les utilisateurs peuvent réutiliser leur code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="63879-p106">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

11. <span data-ttu-id="63879-p107">Pour autoriser les modèles courants de codes confidentiels, tels que les jeux de chiffres séquentiels et répétitifs, activez la case à cocher **Autoriser les modèles courants**. Si vous ne sélectionnez pas cette option, seuls les modèles complexes de chiffres sont autorisés. Par défaut, seuls les modèles complexes de chiffres sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="63879-p107">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="63879-129">Nous vous recommandons de ne pas autoriser les modèles courants.</span><span class="sxs-lookup"><span data-stu-id="63879-129">We recommend that you do not allow common patterns.</span></span>

    
    </div>

12. <span data-ttu-id="63879-130">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="63879-130">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

