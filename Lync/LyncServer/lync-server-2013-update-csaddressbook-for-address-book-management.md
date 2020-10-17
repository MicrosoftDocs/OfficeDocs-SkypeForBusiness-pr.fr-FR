---
title: 'Lync Server 2013 : Update-CsAddressBook pour la gestion des carnets d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fdbef7a3826a734262a77aa39fb2ce32e547463
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527701"
---
# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="0c972-102">Update-CsAddressBook pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c972-102">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c972-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0c972-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0c972-p101">Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes suivants sont autorisés à exécuter localement l’applet de commande Update-CsAddressBook : RTCUniversalUserAdmins, RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="0c972-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="0c972-p102">L’applet de commande Update-CsAddressBook remplace la commande **abserver.exe –syncNow** d’Office Communications Server. Cette applet de commande sert à lancer une synchronisation immédiatement au lieu d’attendre qu’elle s’effectue à l’heure initialement prévue. Dans le premier exemple, la commande met à jour tous les carnets d’adresses dans l’organisation. Dans le second exemple, elle met uniquement à jour le carnet d’adresses associé au serveur défini.</span><span class="sxs-lookup"><span data-stu-id="0c972-p102">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server. The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time. The first example command updates all Address Books in the organization. The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c972-110">Dans Lync Server 2013, le réplicateur d’utilisateurs Lync Server récupère les modifications à partir d’Active Directory et met à jour la base de données utilisateur Lync Server en fonction d’un intervalle configuré.</span><span class="sxs-lookup"><span data-stu-id="0c972-110">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="0c972-111">Lync Server User Replicator propagera également les modifications à la base de données RTCab rapidement, sans que l’administrateur doive exécuter Update-CSAddressBook.</span><span class="sxs-lookup"><span data-stu-id="0c972-111">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="0c972-112">Les administrateurs devront seulement exécuter Update-CSAddressBook si le téléchargement du fichier de carnet d’adresses est activé.</span><span class="sxs-lookup"><span data-stu-id="0c972-112">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="0c972-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0c972-113">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="0c972-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0c972-114">See Also</span></span>


[<span data-ttu-id="0c972-115">Update-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="0c972-115">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

