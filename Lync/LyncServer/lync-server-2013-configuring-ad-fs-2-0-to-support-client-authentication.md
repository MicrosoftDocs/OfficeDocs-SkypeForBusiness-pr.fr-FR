---
title: 'Lync Server 2013 : configuration d’AD FS 2,0 pour prendre en charge l’authentification client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d2b713d109a72431e78e966258a84c084523a7a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517641"
---
# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="d28a7-102">Configuration d’AD FS 2,0 pour prendre en charge l’authentification client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d28a7-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d28a7-103">_**Dernière modification de la rubrique :** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="d28a7-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="d28a7-104">Il existe deux types d’authentification possibles pouvant être configurés pour permettre à AD FS 2,0 de prendre en charge l’authentification à l’aide de cartes à puce :</span><span class="sxs-lookup"><span data-stu-id="d28a7-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="d28a7-105">Authentification basée sur les formulaires (FBA)</span><span class="sxs-lookup"><span data-stu-id="d28a7-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="d28a7-106">Authentification du client TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="d28a7-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="d28a7-107">À l’aide de l’authentification basée sur les formulaires, vous pouvez développer une page Web qui permet aux utilisateurs de s’authentifier en utilisant leur nom d’utilisateur/mot de passe ou en utilisant leur carte à puce et leur code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="d28a7-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="d28a7-108">Cette rubrique se concentre sur la mise en œuvre de l’authentification du client TLS (Transport Layer Security) avec les services ADFS 2,0.</span><span class="sxs-lookup"><span data-stu-id="d28a7-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="d28a7-109">Pour plus d’informations sur les types d’authentifications AD FS 2,0, voir AD FS 2,0 : comment modifier le type d’authentification local à [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384) .</span><span class="sxs-lookup"><span data-stu-id="d28a7-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="d28a7-110">**Pour configurer AD FS 2,0 afin de prendre en charge l’authentification client**</span><span class="sxs-lookup"><span data-stu-id="d28a7-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="d28a7-111">Connectez-vous à l’ordinateur AD FS 2,0 à l’aide d’un compte d’administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="d28a7-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="d28a7-112">Lancez l’Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="d28a7-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="d28a7-113">Accédez à C : \\ Inetpub \\ ADFS \\ ls.</span><span class="sxs-lookup"><span data-stu-id="d28a7-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="d28a7-114">Effectuez une copie de sauvegarde du fichier web.config existant.</span><span class="sxs-lookup"><span data-stu-id="d28a7-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="d28a7-115">Ouvrez le fichier de web.config existant à l’aide du bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="d28a7-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="d28a7-116">Dans la barre de menus, sélectionnez **modifier** , puis **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="d28a7-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="d28a7-117">Recherchez **\<localAuthenticationTypes\>** .</span><span class="sxs-lookup"><span data-stu-id="d28a7-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="d28a7-118">Notez qu’il existe quatre types d’authentification répertoriés, un par ligne.</span><span class="sxs-lookup"><span data-stu-id="d28a7-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="d28a7-119">Déplacez la ligne contenant le type d’authentification TLSClient en haut de la liste dans la section.</span><span class="sxs-lookup"><span data-stu-id="d28a7-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="d28a7-120">Enregistrez et fermez le fichier web.config.</span><span class="sxs-lookup"><span data-stu-id="d28a7-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="d28a7-121">Lancez une invite de commandes avec des privilèges élevés.</span><span class="sxs-lookup"><span data-stu-id="d28a7-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="d28a7-122">Redémarrez les services Internet (IIS) en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d28a7-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

