---
title: 'Lync Server 2013 : Configuration des paramètres des comptes d’utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4d06405d2f80aef5decb69d564ae399401d4328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a><span data-ttu-id="500e2-102">Configuration des paramètres des comptes d’utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="500e2-102">Configure user account settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="500e2-103">_**Dernière modification de la rubrique:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="500e2-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="500e2-104">Les utilisateurs d’appels entrants doivent entrer un numéro de téléphone ou de poste, ainsi qu’un code confidentiel pour participer à des conférences en qualité d’utilisateurs authentifiés.</span><span class="sxs-lookup"><span data-stu-id="500e2-104">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="500e2-105">L’URI de **ligne** téléphonique spécifié sur les comptes d’utilisateurs de Lync Server est requis pour l’authentification.</span><span class="sxs-lookup"><span data-stu-id="500e2-105">The telephony **Line URI** specified on Lync Server user accounts is required for authentication.</span></span>

<span data-ttu-id="500e2-106">La procédure décrite dans cette rubrique explique comment affecter un **URI de ligne** pour un compte utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="500e2-106">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="500e2-107">Si vous devez attribuer un **URI de ligne** à plusieurs comptes utilisateur, vous pouvez créer un script à l’aide de l’applet de commande **Set-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="500e2-107">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="500e2-108">Pour plus d’informations sur l’utilisation d’un exemple de script pour attribuer un **URI de ligne** à plusieurs comptes d’utilisateur, voir « [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945)attribuer des URI de ligne à plusieurs utilisateurs».</span><span class="sxs-lookup"><span data-stu-id="500e2-108">For details about using a sample script to assign **Line URI** to multiple user accounts, see "Assign Line URIs to Multiple Users" at [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945).</span></span>

<div>

## <a name="to-configure-user-account-settings"></a><span data-ttu-id="500e2-109">Pour configurer les paramètres de compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="500e2-109">To configure user account settings</span></span>

1.  <span data-ttu-id="500e2-110">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-UserAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="500e2-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="500e2-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="500e2-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="500e2-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="500e2-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="500e2-113">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="500e2-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="500e2-114">Dans le champ de recherche, tapez le nom de l’utilisateur à configurer pour une conférence rendez-vous ou cliquez sur **Ajouter un filtre** pour spécifier les champs de la recherche, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="500e2-114">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>

5.  <span data-ttu-id="500e2-115">Double-cliquez sur le nom d’utilisateur pour ouvrir la boîte de dialogue **modifier l’utilisateur de Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="500e2-115">Double-click the user name to open the **Edit Lync Server User** dialog box.</span></span>

6.  <span data-ttu-id="500e2-116">Sous **Téléphonie**, dans le champ **URI de ligne**, tapez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200).</span><span class="sxs-lookup"><span data-stu-id="500e2-116">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="500e2-117">Vous pouvez spécifier un <STRONG>URI de ligne</STRONG> uniquement si l’option <STRONG>Téléphonie</STRONG> est définie sur <STRONG>De PC à PC uniquement</STRONG>, <STRONG>Voix Entreprise</STRONG>, <STRONG>Contrôle d’appel distant</STRONG> ou <STRONG>Contrôle d’appel distant uniquement</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="500e2-117">You can specify <STRONG>Line URI</STRONG> only if <STRONG>Telephony</STRONG> is set to <STRONG>PC-to-PC only</STRONG>, <STRONG>Enterprise Voice</STRONG>, <STRONG>Remote call control</STRONG> or <STRONG>Remote call control only</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="500e2-118">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="500e2-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

