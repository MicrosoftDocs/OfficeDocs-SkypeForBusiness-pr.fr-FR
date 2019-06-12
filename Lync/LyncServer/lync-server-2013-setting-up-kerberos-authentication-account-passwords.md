---
title: 'Lync Server 2013 : Configuration des mots de passe de compte d’authentification Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06ca8bf5d1b3dc90b1ceacbe581e0426b5c0aaa9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="6f4a9-102">Configuration des mots de passe de compte d’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f4a9-102">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f4a9-103">_**Dernière modification de la rubrique:** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="6f4a9-103">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="6f4a9-104">Une fois que vous avez créé l’objet ordinateur pour le compte d’authentification Kerberos, vous pouvez configurer le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="6f4a9-104">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="6f4a9-105">Vous exécutez l’applet de cmdlet Windows PowerShell pour configurer le mot de passe du compte Kerberos sur un serveur.</span><span class="sxs-lookup"><span data-stu-id="6f4a9-105">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="6f4a9-106">Vous pouvez définir le mot de passe sur l’objet que vous avez créé pour l’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="6f4a9-106">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="6f4a9-107">Le mot de passe peut être défini sur une valeur connue, mais par défaut comme un mot de passe aléatoire.</span><span class="sxs-lookup"><span data-stu-id="6f4a9-107">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="6f4a9-108">Le mot de passe est disponible pour toutes les sources d’authentification Kerberos qui utilisent le compte.</span><span class="sxs-lookup"><span data-stu-id="6f4a9-108">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="6f4a9-109">Les applets de cmdlet Windows PowerShell permettent de configurer et de gérer les mots de passe des comptes Kerberos.</span><span class="sxs-lookup"><span data-stu-id="6f4a9-109">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6f4a9-110">L’objet de compte Kerberos est un objet ordinateur, mais il utilise le paramètre UserAccount pour les opérations dans les cmdlets Windows PowerShell qui sont référencées.</span><span class="sxs-lookup"><span data-stu-id="6f4a9-110">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="6f4a9-111">Notez qu’il ne s’agit pas d’une erreur, mais du comportement prévu de l’applet de passe lorsqu’elle est utilisée avec la création et la maintenance du compte Kerberos.</span><span class="sxs-lookup"><span data-stu-id="6f4a9-111">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6f4a9-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6f4a9-112">In This Section</span></span>

  - [<span data-ttu-id="6f4a9-113">Définition d’un mot de passe de compte d’authentification Kerberos sur un serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f4a9-113">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="6f4a9-114">Synchronisation d’un mot de passe de compte d’authentification Kerberos avec les services Internet (IIS) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f4a9-114">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

