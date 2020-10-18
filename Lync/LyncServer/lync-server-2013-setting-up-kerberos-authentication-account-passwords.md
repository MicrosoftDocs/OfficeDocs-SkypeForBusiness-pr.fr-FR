---
title: 'Lync Server 2013 : configuration des mots de passe de compte d’authentification Kerberos'
description: 'Lync Server 2013 : configuration des mots de passe de compte d’authentification Kerberos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614b1411f9454c39843f4e69cabbfc3b02986e51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577220"
---
# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="1010b-103">Configuration des mots de passe de compte d’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1010b-103">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1010b-104">_**Dernière modification de la rubrique :** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="1010b-104">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="1010b-105">Après avoir créé l’objet ordinateur pour le compte d’authentification Kerberos, vous pouvez configurer le mot de passe pour le compte.</span><span class="sxs-lookup"><span data-stu-id="1010b-105">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="1010b-106">Vous exécutez l’applet de commande Windows PowerShell pour définir le mot de passe du compte Kerberos sur un serveur.</span><span class="sxs-lookup"><span data-stu-id="1010b-106">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="1010b-107">Vous pouvez définir le mot de passe sur l’objet créé pour l’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1010b-107">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="1010b-108">Le mot de passe peut être défini sur une valeur connue, mais par défaut il s’agit d’un mot de passe aléatoire.</span><span class="sxs-lookup"><span data-stu-id="1010b-108">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="1010b-109">Il est valable pour toutes les sources d’authentification Kerberos qui utilisent le compte.</span><span class="sxs-lookup"><span data-stu-id="1010b-109">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="1010b-110">Vous utilisez les applets de commande Windows PowerShell pour configurer et gérer les mots de passe de compte Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1010b-110">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1010b-111">L’objet de compte Kerberos est un objet ordinateur, mais il utilise le paramètre UserAccount pour les opérations des applets de commande Windows PowerShell référencées.</span><span class="sxs-lookup"><span data-stu-id="1010b-111">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="1010b-112">Notez qu’il ne s’agit pas d’une erreur, mais du comportement prévu de l’applet de commande lorsqu’elle est utilisée pour la création et la maintenance du compte Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1010b-112">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1010b-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="1010b-113">In This Section</span></span>

  - [<span data-ttu-id="1010b-114">Définir un mot de passe de compte d’authentification Kerberos sur un serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1010b-114">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="1010b-115">Synchronisation d’un mot de passe de compte d’authentification Kerberos avec les services Internet (IIS) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1010b-115">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

