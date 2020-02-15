---
title: 'Lync Server 2013 : rapport d’inventaire de téléphonie IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c99945626105282324202d1fd754cd5d966bc81
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="720d0-102">Rapport d’inventaire de téléphonie IP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="720d0-102">IP Phone Inventory Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="720d0-103">_**Dernière modification de la rubrique :** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="720d0-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="720d0-p101">Le Rapport d’inventaire de téléphonie IP fournit des informations sur les téléphones IP en cours d’utilisation dans votre organisation. Il offre une liste détaillée des téléphones IP qui ont été utilisées durant la période de rapport spécifiée. Entre autres choses, il permet aux administrateurs de savoir s’il existe des téléphones obsolètes qui doivent être remplacés. Il peut également les alerter quant à la présence de téléphones coûteux rarement utilisés. Ce type d’informations peut être précieux dans le cadre de l’achat de nouveaux téléphones ou de la redistribution des téléphones existants (par exemple, il peut être demandé à un utilisateur qui n’utilise son téléphone coûteux que très rarement de l’échanger avec un autre utilisateur qui utilise le sien beaucoup plus fréquemment).</span><span class="sxs-lookup"><span data-stu-id="720d0-p101">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization. The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period. Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used. That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones. (For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="720d0-109">Il convient de noter que ce rapport présente quelques limitations lorsqu’il est utilisé comme un véritable rapport d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="720d0-109">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="720d0-110">Pour une chose, le rapport de téléphone IP répertorie simplement tous les téléphones qui se sont connectés à Lync Server pendant la période spécifiée, triés par date de la dernière connexion.</span><span class="sxs-lookup"><span data-stu-id="720d0-110">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="720d0-111">Si un téléphone ne s’est pas connecté pendant la période spécifiée, il ne figurera pas dans le rapport d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="720d0-111">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="720d0-112">Cela inclut les téléphones qui se sont connectés avant la période de démarrage et qui étaient encore connectés pendant l’intervalle de temps spécifié.</span><span class="sxs-lookup"><span data-stu-id="720d0-112">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="720d0-113">Par exemple, supposons que vous souhaitiez consulter tout l’inventaire téléphonique pour juillet, 2012.</span><span class="sxs-lookup"><span data-stu-id="720d0-113">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="720d0-114">Supposons également que plusieurs téléphones ont ouvert une session sur Lync Server le 30 juin 2012 et ont toujours ouvert une session depuis le 1er juillet.</span><span class="sxs-lookup"><span data-stu-id="720d0-114">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="720d0-115">Ces téléphones ne s’afficheront pas dans le rapport d’inventaire pour le 1er juillet.</span><span class="sxs-lookup"><span data-stu-id="720d0-115">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="720d0-p103">Il convient également de noter que le rapport d’inventaire pourrait inclure des téléphones que votre organisation n’utilise plus. Supposez par exemple que plusieurs téléphones Fabrikam se sont connectés au système le 1er juillet 2012 ; cinq jours plus tard, votre organisation s’est débarrassé de tous ces téléphones Fabrikam et les a remplacé par un modèle Contoso plus récent. Les téléphones Fabrikam apparaîtront tout de même dans le rapport d’inventaire simplement du fait qu’ils se sont connectés au système durant le mois de juillet.</span><span class="sxs-lookup"><span data-stu-id="720d0-p103">It's also important to note that the inventory report could include phones that your organization no longer uses. For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model. The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="720d0-p104">En outre, le Rapport d’inventaire de téléphonie IP ne fournit aucun total récapitulatif pour les différents types de téléphones. Par exemple, supposez que vous avez 105 téléphones Polycom CX600. Le rapport ne vous indiquera pas que vous avez 105 de ces téléphones ; au lieu de cela, vous verrez simplement 105 entrées distinctes pour le Polycom Cx600. Le seul moyen de savoir qu’il y a 105 entrées pour le Polycom Cx600 serait de compter chacune de ces entrées manuellement.</span><span class="sxs-lookup"><span data-stu-id="720d0-p104">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones. For example, suppose you have 105 Polycom CX600 phones. The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600. The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="720d0-123">Vous pourriez également exporter les données et utiliser Microsoft Excel ou Windows PowerShell pour compter les entrées à votre place.</span><span class="sxs-lookup"><span data-stu-id="720d0-123">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="720d0-124">Accès au Rapport d’inventaire de téléphonie IP</span><span class="sxs-lookup"><span data-stu-id="720d0-124">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="720d0-p105">Le Rapport d’inventaire de téléphonie IP est accessible à partir de la page d’accueil des Rapports de surveillance. Un clic sur la métrique URI utilisateur vous permet d’accéder au Rapport d’activité de l’utilisateur. Un clic sur la métrique Dernière activité pour appel d’égal à égal permet d’accéder au Rapport détaillé de session d’égal à égal ; un clic sur cette même métrique pour une conférence permet d’accéder au Rapport détaillé de conférence.</span><span class="sxs-lookup"><span data-stu-id="720d0-p105">The IP Phone Inventory Report is accessed from the Monitoring Reports home page. If you click the User URI metric you can access the User Activity Report for that user. Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="720d0-128">Utilisation optimale du Rapport d’inventaire de téléphonie IP</span><span class="sxs-lookup"><span data-stu-id="720d0-128">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="720d0-129">Si vous êtes intéressé uniquement par les informations d’utilisation d’un type de téléphone particulier (par exemple, « quelle est la fréquence d’utilisation d’un téléphone Polycom CX600 ? »), vous pouvez obtenir ces informations directement à partir du rapport d’inventaire de téléphonie IP en filtrant ce type particulier de téléphone.</span><span class="sxs-lookup"><span data-stu-id="720d0-129">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="720d0-130">En revanche, si vous souhaitez obtenir des données de synthèse pour tous vos téléphones (combien de personnes utilisent un Polycom CX600, combien utilisent un LG-Nortel IP8540, et ainsi de suite.), vous devrez exporter les données et utiliser une autre application (telle que Windows PowerShell) pour effectuer ce type d’analyse.</span><span class="sxs-lookup"><span data-stu-id="720d0-130">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="720d0-131">Par exemple, supposons que vous exportez les données vers un fichier de valeurs séparées\\par\\des\_virgules\_(C : Data IP\_report report. csv).</span><span class="sxs-lookup"><span data-stu-id="720d0-131">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="720d0-132">Dans ce cas, vous pourriez utiliser les deux commandes suivantes pour obtenir des données de synthèse pour tous vos téléphones :</span><span class="sxs-lookup"><span data-stu-id="720d0-132">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="720d0-133">Les données retournées se présentent ainsi :</span><span class="sxs-lookup"><span data-stu-id="720d0-133">That will return data similar to this:</span></span>

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

<span data-ttu-id="720d0-134">De mêmes, ces deux commandes indiquent quels téléphones se sont connectés au système mais n’ont jamais été utilisés pour effectuer un appel (la valeur de la métrique Dernière activité est vierge, ce qui indique l’absence de dernière activité) :</span><span class="sxs-lookup"><span data-stu-id="720d0-134">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="720d0-135">Cette commande renvoie des données semblables aux suivantes pour chaque téléphone qui n’a pas été utilisé :</span><span class="sxs-lookup"><span data-stu-id="720d0-135">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="720d0-136">Le Rapport d’inventaire de téléphonie IP offre un autre avantage : si vous connaissez l’adresse MAC d’un téléphone IP, vous pouvez identifier le dernier utilisateur ayant utilisé ce téléphone en entrant simplement cette adresse dans la zone de texte Adresse MAC.</span><span class="sxs-lookup"><span data-stu-id="720d0-136">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="720d0-137">Le Rapport d’inventaire de téléphonie IP indiquera alors (entre autres choses) l’adresse SIP du dernier utilisateur qui s’est connecté avec ce téléphone.</span><span class="sxs-lookup"><span data-stu-id="720d0-137">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="720d0-138">En guise d’alternative, vous pouvez entrer l’adresse SIP d’un utilisateur (dans la zone Préfixe d’URI de l’utilisateur) pour dresser la liste de tous les téléphones qui ont été utilisés par cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="720d0-138">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="720d0-139">Filtres</span><span class="sxs-lookup"><span data-stu-id="720d0-139">Filters</span></span>

<span data-ttu-id="720d0-p108">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, avec le rapport d’inventaire de téléphonie IP il est possible d’afficher uniquement les téléphones fabriqués par une société spécifique ou même une version spécifique de ces téléphones. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les inscriptions sont groupées par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="720d0-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones. You can also choose how data should be grouped. In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="720d0-144">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’inventaire de téléphonie IP.</span><span class="sxs-lookup"><span data-stu-id="720d0-144">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="720d0-145">Filtres de rapport d’inventaire de téléphonie IP</span><span class="sxs-lookup"><span data-stu-id="720d0-145">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="720d0-146">Nom</span><span class="sxs-lookup"><span data-stu-id="720d0-146">Name</span></span></th>
<th><span data-ttu-id="720d0-147">Description</span><span class="sxs-lookup"><span data-stu-id="720d0-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="720d0-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-p109">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="720d0-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="720d0-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="720d0-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="720d0-p110">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="720d0-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="720d0-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="720d0-154">7/7/2012</span></span></p>
<p><span data-ttu-id="720d0-155">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="720d0-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="720d0-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="720d0-156">7/3/2012</span></span></p>
<p><span data-ttu-id="720d0-157">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="720d0-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="720d0-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-p111">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="720d0-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="720d0-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="720d0-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="720d0-p112">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="720d0-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="720d0-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="720d0-164">7/7/2012</span></span></p>
<p><span data-ttu-id="720d0-165">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="720d0-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="720d0-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="720d0-166">7/3/2012</span></span></p>
<p><span data-ttu-id="720d0-167">Les semaines commencent le dimanche et se terminent le samedi.</span><span class="sxs-lookup"><span data-stu-id="720d0-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="720d0-168"><strong>Constructeur</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-168"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-p113">Nom de la société ayant fabriqué le téléphone IP. Les valeurs pour ce filtre sont remplies automatiquement pour vous en fonction des téléphones IP actuellement présents dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="720d0-p113">Name of the company that manufactured the IP phone. The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="720d0-171"><strong>Version du matériel</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-171"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-172">Numéro de version du téléphone IP ; les filtres Fabricant et Version du matériel vous permettent d’identifier de manière unique un type de téléphone particulier.</span><span class="sxs-lookup"><span data-stu-id="720d0-172">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="720d0-173">Les valeurs pour ce filtre sont remplies automatiquement pour vous en fonction des téléphones IP actuellement présents dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="720d0-173">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="720d0-174"><strong>Agent utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-174"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-p115">Identifiant du logiciel utilisé par le téléphone IP. Les valeurs pour ce filtre sont remplies automatiquement pour vous en fonction des téléphones IP actuellement présents dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="720d0-p115">Identifier for the software used by the IP phone. The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="720d0-177"><strong>Adresse MAC</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-177"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-p116">Identifiant unique de l’interface réseau sur le téléphone IP. L’adresse MAC (Media Access Control) est généralement assignée lors de la fabrication du téléphone ; elle est codée en dur dans le matériel du périphérique.</span><span class="sxs-lookup"><span data-stu-id="720d0-p116">Unique identifier for the network interface on the IP phone. The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="720d0-p117">Pour rechercher des enregistrements associés à une adresse MAC spécifique, il vous suffit d’entrer cette adresse. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="720d0-p117">To search for records pertaining to a specific MAC address simply enter that address. For example:</span></span></p>
<p><span data-ttu-id="720d0-182">00-08-5D-16-16-48</span><span class="sxs-lookup"><span data-stu-id="720d0-182">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="720d0-p118">Vous devez entrer l’adresse complète. Une adresse partielle (par exemple 00-08-5D) ne renvoie aucune donnée.</span><span class="sxs-lookup"><span data-stu-id="720d0-p118">You must enter the complete address. A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="720d0-185"><strong>Dernière activité avant les jours</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-185"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-186">Sélectionnez l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="720d0-186">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="720d0-187">Tous les</span><span class="sxs-lookup"><span data-stu-id="720d0-187">[All]</span></span></p></li>
<li><p><span data-ttu-id="720d0-188">10 </span><span class="sxs-lookup"><span data-stu-id="720d0-188">10</span></span></p></li>
<li><p><span data-ttu-id="720d0-189">vingtaine</span><span class="sxs-lookup"><span data-stu-id="720d0-189">20</span></span></p></li>
<li><p><span data-ttu-id="720d0-190">0,30</span><span class="sxs-lookup"><span data-stu-id="720d0-190">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="720d0-191"><strong>Heure de la dernière fermeture de session avant les jours</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-191"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-192">Sélectionnez l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="720d0-192">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="720d0-193">Tous les</span><span class="sxs-lookup"><span data-stu-id="720d0-193">[All]</span></span></p></li>
<li><p><span data-ttu-id="720d0-194">10 </span><span class="sxs-lookup"><span data-stu-id="720d0-194">10</span></span></p></li>
<li><p><span data-ttu-id="720d0-195">vingtaine</span><span class="sxs-lookup"><span data-stu-id="720d0-195">20</span></span></p></li>
<li><p><span data-ttu-id="720d0-196">0,30</span><span class="sxs-lookup"><span data-stu-id="720d0-196">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="720d0-197"><strong>Préfixe URI de l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-197"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-198">Adresse SIP de l’utilisateur qui a utilisé le téléphone IP.</span><span class="sxs-lookup"><span data-stu-id="720d0-198">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="720d0-199">Mesures</span><span class="sxs-lookup"><span data-stu-id="720d0-199">Metrics</span></span>

<span data-ttu-id="720d0-200">Le tableau qui suit répertorie les informations fournies dans le rapport d’inventaire de téléphonie IP.</span><span class="sxs-lookup"><span data-stu-id="720d0-200">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="720d0-201">Mesures du rapport d’inventaire de téléphonie IP</span><span class="sxs-lookup"><span data-stu-id="720d0-201">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="720d0-202">Nom</span><span class="sxs-lookup"><span data-stu-id="720d0-202">Name</span></span></th>
<th><span data-ttu-id="720d0-203">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="720d0-203">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="720d0-204">Description</span><span class="sxs-lookup"><span data-stu-id="720d0-204">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="720d0-205"><strong>Constructeur</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-205"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-206">Oui</span><span class="sxs-lookup"><span data-stu-id="720d0-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="720d0-207">Nom de la société ayant fabriqué le téléphone IP.</span><span class="sxs-lookup"><span data-stu-id="720d0-207">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="720d0-208"><strong>Version du matériel</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-208"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-209">Oui</span><span class="sxs-lookup"><span data-stu-id="720d0-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="720d0-210">Numéro de version du téléphone IP.</span><span class="sxs-lookup"><span data-stu-id="720d0-210">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="720d0-211"><strong>Adresse MAC</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-211"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-212">Oui</span><span class="sxs-lookup"><span data-stu-id="720d0-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="720d0-p119">Identifiant unique de l’interface réseau sur le téléphone IP. L’adresse MAC est généralement assignée lors de la fabrication du téléphone ; elle est codée en dur dans le matériel du périphérique.</span><span class="sxs-lookup"><span data-stu-id="720d0-p119">Unique identifier for the network interface on the IP phone. The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="720d0-215"><strong>URI utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-215"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-216">Oui</span><span class="sxs-lookup"><span data-stu-id="720d0-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="720d0-217">Adresse SIP de l’utilisateur qui a utilisé le téléphone IP.</span><span class="sxs-lookup"><span data-stu-id="720d0-217">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="720d0-218"><strong>Agent utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-218"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-219">Oui</span><span class="sxs-lookup"><span data-stu-id="720d0-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="720d0-220">Identifiant du logiciel utilisé par le téléphone IP.</span><span class="sxs-lookup"><span data-stu-id="720d0-220">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="720d0-221"><strong>Heure de la dernière ouverture de session</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-221"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-222">Oui</span><span class="sxs-lookup"><span data-stu-id="720d0-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="720d0-223">Date et heure de la dernière connexion du téléphone IP à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="720d0-223">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="720d0-224"><strong>Heure de la dernière fermeture de session</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-224"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-225">Oui</span><span class="sxs-lookup"><span data-stu-id="720d0-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="720d0-226">Date et heure de la dernière déconnexion de Lync Server par le téléphone IP.</span><span class="sxs-lookup"><span data-stu-id="720d0-226">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="720d0-227"><strong>Dernière activité</strong></span><span class="sxs-lookup"><span data-stu-id="720d0-227"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="720d0-228">Oui</span><span class="sxs-lookup"><span data-stu-id="720d0-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="720d0-229">Date et heure de la dernière utilisation de ce téléphone IP.</span><span class="sxs-lookup"><span data-stu-id="720d0-229">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

