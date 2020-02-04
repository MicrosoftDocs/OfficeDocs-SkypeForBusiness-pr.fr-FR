---
title: 'Lync Server 2013 : New-CsAddressBookConfiguration pour la gestion du carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsAddressBookConfiguration for Address Book management
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48184985
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e69c1ea9c68dfacb68ada70d4f7643b2777f062f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="27012-102">Nouveauté-CsAddressBookConfiguration pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27012-102">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27012-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="27012-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="27012-104">Qui peut exécuter cette applet de commande : par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande New-CsAddressBookConfiguration : RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="27012-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="27012-105">Pour renvoyer la liste de tous les rôles de contrôle d’accès basés sur des rôles (RBAC) affectés à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="27012-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

<span data-ttu-id="27012-106">L’applet de nouvelle applet de nouveau-CsAddressBookConfiguration crée une nouvelle configuration pour gérer le comportement du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="27012-106">The New-CsAddressBookConfiguration cmdlet creates a new configuration to manage the behavior of the Address book.</span></span> <span data-ttu-id="27012-107">Spécifiques à cette applet de commande permet de définir si le service de carnet d’adresses crée les fichiers de téléchargement du client, la façon dont les règles de normalisation sont utilisées et la durée de conservation des fichiers delta et compacts, ainsi que la taille du fichier Delta heure de la journée de création du carnet d’adresses du fichier complet et ce qu’il doit être de la synchronisation des informations de la base de données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="27012-107">Specific to this cmdlet is the ability to define if the Address Book Service creates the client download files, how and if normalization rules are used, how long to retain delta and compact delta files, delta file size before incorporating a new full file creation, what time of day the full file Address Book is created, and what the internal should be for synchronization of information in the User database.</span></span>

<span data-ttu-id="27012-108">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="27012-108">For example:</span></span>

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a><span data-ttu-id="27012-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="27012-109">See Also</span></span>


[<span data-ttu-id="27012-110">New-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="27012-110">New-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

