---
title: 'Lync Server 2013 : exécution et surveillance de sauvegardes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3181a266e5792d190186e9f09b2cab5852156cbe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="6f5f7-102">Exécution et analyse des sauvegardes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f5f7-102">Performing and monitoring backups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f5f7-103">_**Dernière modification de la rubrique :** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="6f5f7-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="6f5f7-104">Les priorités de votre entreprise doivent conduire à la spécification des exigences de sauvegarde et de restauration pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-104">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="6f5f7-105">La sauvegarde des serveurs et des données est la première ligne de défense de la planification d’un sinistre.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-105">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="6f5f7-106">Les ordinateurs qui exécutent les services ou rôles serveur Lync Server 2013 doivent avoir une copie de la topologie actuelle, des paramètres de configuration actuels et des stratégies actuelles pour pouvoir fonctionner dans leur rôle désigné.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-106">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="6f5f7-107">Lync Server est tenu de s’assurer que ces informations sont transmises à chaque ordinateur qui en a besoin.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-107">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="6f5f7-108">Les applets **de suivi Export-CsConfiguration** et **Import-CsConfiguration** sont utilisés pour sauvegarder et restaurer votre topologie de serveur Lync, vos paramètres de configuration et vos stratégies lors d’une mise à niveau centralisée du magasin.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-108">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="6f5f7-109">Les applets **de passe Export-CsConfiguration** vous permettent d’exporter des données vers un. Fichier ZIP.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-109">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="6f5f7-110">Vous pouvez ensuite utiliser l’applet de cmdlet **Import-CsConfiguration** pour la lire. ZIP et restaurez la topologie, les paramètres de configuration et les stratégies dans le centre de gestion central.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-110">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="6f5f7-111">Après cela, les services de réplication de Lync Server répliquent les informations restaurées sur d’autres ordinateurs exécutant des services serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-111">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="6f5f7-112">La possibilité d’exporter et d’importer des données de configuration est également utilisée lors de la configuration initiale d’ordinateurs situés dans votre réseau de périmètre (par exemple, serveurs de périphérie).</span><span class="sxs-lookup"><span data-stu-id="6f5f7-112">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="6f5f7-113">Lorsque vous configurez un ordinateur dans le réseau de périmètre, vous devez d’abord effectuer une réplication manuelle à l’aide des applets de commande CsConfiguration : vous devez exporter les données de configuration en utilisant **Export-CsConfiguration** , puis copier le. ZIP vers l’ordinateur dans le réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-113">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="6f5f7-114">Après cela, vous pouvez utiliser **Import-CsConfiguration** et le paramètre LocalStore pour importer les données.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-114">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="6f5f7-115">Vous ne devez effectuer cette opération qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-115">You only have to do this one time.</span></span> <span data-ttu-id="6f5f7-116">Après cela, la réplication sera exécutée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-116">After that, replication will occur automatically.</span></span>

<span data-ttu-id="6f5f7-117">Qui peut exécuter cette applet de commande : par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande **Export-CsConfiguration** localement : RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-117">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="6f5f7-118">Pour renvoyer la liste de tous les rôles RBAC, cette applet de commande est affectée (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="6f5f7-118">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="6f5f7-119">Toutes les bases de données principales SQL 2012 doivent être sauvegardées conformément aux [meilleures pratiques SQL](http://go.microsoft.com/fwlink/p/?linkid=290716).</span><span class="sxs-lookup"><span data-stu-id="6f5f7-119">All SQL 2012 Back End databases should be backed up as per [SQL best practices](http://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="6f5f7-120">Le test régulier du plan de reprise après sinistre pour votre infrastructure Lync Server 2013 doit être effectué dans un environnement de laboratoire qui imite l’environnement de production aussi fidèlement que possible.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-120">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="6f5f7-121">Pour plus d’informations sur les tests de récupération d’urgence, reportez-vous aux tâches mensuelles.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-121">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="6f5f7-122">Notez que la fréquence de sauvegarde peut être ajustée en fonction de vos objectifs en matière de points de restauration et de points de récupération.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-122">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="6f5f7-123">Nous vous conseillons de prendre des instantanés périodiques et périodiques tout au long de la journée.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-123">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="6f5f7-124">En règle générale, vous devez effectuer des sauvegardes complètes toutes les 24 heures.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-124">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6f5f7-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6f5f7-125">See Also</span></span>


[<span data-ttu-id="6f5f7-126">Importation-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="6f5f7-126">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="6f5f7-127">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="6f5f7-127">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="6f5f7-128">Meilleures pratiques SQL</span><span class="sxs-lookup"><span data-stu-id="6f5f7-128">SQL best practices</span></span>](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

