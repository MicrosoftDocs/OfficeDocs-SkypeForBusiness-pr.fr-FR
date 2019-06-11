---
title: 'Lync Server 2013: configuration d’AD FS 2,0 pour prendre en charge l’authentification du client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12f7cad4b36eb96f7b36925aa91e6363b8cdd264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="c5251-102">Configuration de la 2,0 AD FS pour prendre en charge l’authentification client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5251-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5251-103">_**Dernière modification de la rubrique:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="c5251-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="c5251-104">Deux types d’authentifications peuvent être configurés pour permettre à AD FS 2.0 de prendre en charge l’authentification à l’aide de cartes à puce :</span><span class="sxs-lookup"><span data-stu-id="c5251-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="c5251-105">Authentification basée sur les formulaires</span><span class="sxs-lookup"><span data-stu-id="c5251-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="c5251-106">Authentification de client TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="c5251-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="c5251-107">L’authentification basée sur les formulaires permet de développer une page web permettant aux utilisateurs de s’authentifier à l’aide de leur nom d’utilisateur et de leur mot de passe ou de leur carte à puce et de leur code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="c5251-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="c5251-108">Cette rubrique décrit la mise en œuvre de l’authentification de client TLS (Transport Layer Security) avec AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="c5251-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="c5251-109">Pour plus d’informations sur les types d’authentifications 2,0 d’AD FS, voir AD FS 2,0: Comment changer le [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)type d’authentification locale à.</span><span class="sxs-lookup"><span data-stu-id="c5251-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="c5251-110">**Pour configurer AD FS 2.0 pour prendre en charge l’authentification du client**</span><span class="sxs-lookup"><span data-stu-id="c5251-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="c5251-111">Connectez-vous à l’ordinateur AD FS 2.0 à l’aide d’un compte d’administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="c5251-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="c5251-112">Lancez l’Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="c5251-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="c5251-113">Naviguez jusqu’à\\C\\:\\Inetpub adfs ls</span><span class="sxs-lookup"><span data-stu-id="c5251-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="c5251-114">Effectuez une copie de sauvegarde du fichier web.config existant.</span><span class="sxs-lookup"><span data-stu-id="c5251-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="c5251-115">Ouvrez le fichier web.config existant à l’aide du Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="c5251-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="c5251-116">Dans la barre de menus, sélectionnez **Edition**, puis **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="c5251-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="c5251-117">Recherchez \*\* \<localAuthenticationTypes\>\*\*.</span><span class="sxs-lookup"><span data-stu-id="c5251-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="c5251-118">Quatre types d’authentification s’affichent (un par ligne).</span><span class="sxs-lookup"><span data-stu-id="c5251-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="c5251-119">Déplacez la ligne contenant le type d’authentification TLSClient au début de la liste dans la section.</span><span class="sxs-lookup"><span data-stu-id="c5251-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="c5251-120">Enregistrez et fermez le fichier web.config.</span><span class="sxs-lookup"><span data-stu-id="c5251-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="c5251-121">Lancez une invite de commandes avec des droits élevés.</span><span class="sxs-lookup"><span data-stu-id="c5251-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="c5251-122">Redémarrez IIS en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c5251-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

