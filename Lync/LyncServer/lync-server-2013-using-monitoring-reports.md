---
title: 'Lync Server 2013: utilisation des rapports d’analyse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b7c1e70a47e3f3043215e1d16e1f01bfec4b677
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-monitoring-reports-in-lync-server-2013"></a><span data-ttu-id="37d16-102">Utilisation de rapports d’analyse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37d16-102">Using Monitoring Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37d16-103">_**Dernière modification de la rubrique:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="37d16-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="37d16-104">Lync Server 2013 inclut un ensemble de rapports standard publiés par le service Microsoft SQL Server Reporting.</span><span class="sxs-lookup"><span data-stu-id="37d16-104">Lync Server 2013 includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="37d16-105">Ces rapports, accessibles avec un navigateur web, fournissent des informations d’utilisation, de diagnostic d’appel et de qualité du média basées sur les enregistrements CDR (Enregistrement des détails des appels) et les enregistrements QoE (qualité de l’expérience) qui sont stockés dans les bases de données CDR et QoE.</span><span class="sxs-lookup"><span data-stu-id="37d16-105">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>

<span data-ttu-id="37d16-106">Pour pouvoir utiliser ces rapports, vous devez installer des rapports d’analyse sur un ordinateur exécutant une instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="37d16-106">In order to use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="37d16-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="37d16-107">In This Section</span></span>

  - <span data-ttu-id="37d16-108">[Le tableau de bord de surveillance de Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   fournit aux administrateurs un aperçu rapide de l’intégrité du système et de l’utilisation du système.</span><span class="sxs-lookup"><span data-stu-id="37d16-108">[Using the Monitoring Dashboard in Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   Provides administrators with a quick overview of their system health and system usage.</span></span>

  - <span data-ttu-id="37d16-109">[Les rapports sur l’utilisation du système dans Lync Server 2013](lync-server-2013-system-usage-reports.md)   fournissent des informations sur l’utilisation du système sur la base des données CDR collectées par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37d16-109">[System usage reports in Lync Server 2013](lync-server-2013-system-usage-reports.md)   Provides system usage information based on CDR data collected by Lync Server.</span></span>

  - <span data-ttu-id="37d16-110">[Les rapports de diagnostic des appels (par utilisateur) dans Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   fournissent des informations par utilisateur sur les sessions d’égal à égal et de conférence qui ont échoué.</span><span class="sxs-lookup"><span data-stu-id="37d16-110">[Call Diagnostic Reports (per user) in Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="37d16-111">[Les rapports de diagnostic des appels dans Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   fournissent des informations de synthèse et des données de diagnostic pour les sessions d’égal à égal et de conférence.</span><span class="sxs-lookup"><span data-stu-id="37d16-111">[Call Diagnostic Reports in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="37d16-112">[Rapports de diagnostic de qualité multimédia dans Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   fournit des informations sur la qualité des appels, ainsi que des informations de diagnostic et de dépannage pour les appels en échec.</span><span class="sxs-lookup"><span data-stu-id="37d16-112">[Media Quality Diagnostic Reports in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>

</div>

<div>

## <a name="locating-records"></a><span data-ttu-id="37d16-113">Recherche d’enregistrements</span><span class="sxs-lookup"><span data-stu-id="37d16-113">Locating Records</span></span>

<span data-ttu-id="37d16-p102">Les rapports de surveillance affichent uniquement une quantité limitée d’enregistrements à l’écran. La quantité réelle d’enregistrements affichés sur un écran dépend du rapport. Pour visualiser les enregistrements qui ne sont pas affichés actuellement à l’écran, vous pouvez utiliser les contrôles standard « Précédent » et « Suivant » (qui se trouvent dans la barre d’outils de chaque rapport) qui vous permettent de parcourir les données. Vous pouvez également accéder rapidement à la première ou dernière page du jeu de données.</span><span class="sxs-lookup"><span data-stu-id="37d16-p102">Monitoring Reports only show a limited number of records on the screen at any one time. The actual number of records displayed on a screen varies depending on the report. To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report’s toolbar) that enable you to page through the data. You can also quickly jump to the first page or the last page of the dataset.</span></span>

<span data-ttu-id="37d16-118">Outre ces contrôles, vous pouvez accéder à une page quelconque du jeu de données en tapant simplement son numéro dans la zone **Page actuelle**, puis en appuyant sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="37d16-118">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>

<span data-ttu-id="37d16-p103">Chaque rapport offre également une possibilité limitée de rechercher des enregistrements. Pour rechercher des enregistrements sur la base d’une valeur donnée, tapez cette valeur dans la zone **Rechercher**, puis cliquez sur **Rechercher**. Le rapport commence à explorer les données et s’arrête sur la première instance de la valeur que vous avez entrée dans la zone **Rechercher**. Pour trouver l’enregistrement suivant qui répond aux critères de recherche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="37d16-p103">In addition to providing the ability to page through the data, each report also includes the limited ability to find records. To find records based on a given value, type that value into the **Find** box, and then click **Find**. The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box. To find the next record that meets the search criteria, click **Next**.</span></span>

<span data-ttu-id="37d16-p104">Comme mentionné plus haut, les rapports de surveillance procurent uniquement des fonctionnalités de recherche de base. Par exemple, vous ne pouvez pas spécifier le champ dans lequel rechercher la valeur. Le mécanisme de recherche des valeurs correspondantes dans chaque champ de chaque enregistrement. Vous ne pouvez pas utiliser de caractères génériques dans vos recherches et toutes les recherches tentent de trouver des valeurs partielles. Cela signifie que si vous recherchez 111, la recherche renvoie la valeur 111, ainsi que les valeurs 11100, 811, 3112, 611A5B et tout autre champ qui comprend la valeur 111 n’importe où.</span><span class="sxs-lookup"><span data-stu-id="37d16-p104">As noted, the Monitoring Reports provide only the most basic search functions. For example, you cannot specify which field the value should be found in. The search mechanism automatically searches for matching values in every field in every record. You cannot use wildcards in your searches, and all searches look for partial values. That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>

<span data-ttu-id="37d16-p105">Chaque rapport est configuré de façon à afficher un ensemble d’enregistrements par défaut. Par exemple, par défaut le rapport Enregistrement d’utilisateur montre les activités d’enregistrement des utilisateurs pour la semaine passée. Dans certains cas, il se peut que le rapport soit vide, ce qui signifie qu’aucun enregistrement utilisateur n’a eu lieu durant la semaine passée. Si le message « Aucun résultat ne correspond aux filtres du rapport » s’affiche, essayez de modifier les valeurs de filtre (par exemple, sélectionnez le mois dernier plutôt que la semaine dernière comme période) et réexécutez la requête. Pour plus d’informations, reportez-vous à la section « Filtrage des données » dans la suite de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="37d16-p105">Each report is configured to show a default set of records. For example, by default the User Registration Report shows user registration activities for the past week. In some cases, this might result in a report that returns no records. In this case, it means that no user registrations have taken place in the past week. If you see the message “No results match the report filters,” try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query. For details, see the "Filtering Data" section later in this topic.</span></span>

</div>

<div>

## <a name="filtering-data"></a><span data-ttu-id="37d16-134">Filtrage des données</span><span class="sxs-lookup"><span data-stu-id="37d16-134">Filtering Data</span></span>

<span data-ttu-id="37d16-p106">Il se peut parfois que vous souhaitiez examiner uniquement un sous-ensemble d’enregistrements, par exemple, les sessions P2P plutôt que les sessions de conférence ET P2P. De même, il se peut que vous deviez réduire le nombre d’enregistrements renvoyés. Par défaut, un rapport ne peut afficher que les 1 000 premiers enregistrements d’un jeu de données. Pour faire face à ces cas de figure, la plupart des rapports proposent plusieurs options de filtrage. Par exemple, si vous souhaitez afficher uniquement les enregistrements compris entre le 1er janvier 2011 et le 15 janvier 2011, vous pouvez entrer la date du 1er janvier 2011 dans la zone **De** et la date du 15 janvier 2011 dans la zone **À**. Si vous cliquez ensuite sur **Afficher le rapport**, les données renvoyées se limitent aux activités ayant eu lieu entre le 1er et le 15 janvier 2011.</span><span class="sxs-lookup"><span data-stu-id="37d16-p106">There will likely be times when you want to look at only a subset of records. For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions. Likewise, there will be times when you need to reduce the number of records that are returned. By default, a report can only display the first 1,000 records in a data set. To address these issues, most reports include a number of filtering options. For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box. If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>

<span data-ttu-id="37d16-p107">Les filtres à votre disposition dépendent du rapport que vous visualisez. Pour plus d’informations sur un rapport spécifique, reportez-vous à la rubrique d’aide relative à ce rapport.</span><span class="sxs-lookup"><span data-stu-id="37d16-p107">The filters available to you vary depending on the report that you are viewing. For details about a specific report, see the help topic for that report.</span></span>

</div>

<div>

## <a name="exporting-data"></a><span data-ttu-id="37d16-144">Exportation de données</span><span class="sxs-lookup"><span data-stu-id="37d16-144">Exporting Data</span></span>

<span data-ttu-id="37d16-p108">Les rapports de surveillance fournissent au moins deux manières différentes d’exporter les données incluses dans un rapport. Vous pouvez utiliser l’option **Exporter** de la barre d’outils affichée en haut de chaque rapport. Pour utiliser cette option, sélectionnez le format d’exportation souhaité dans la liste déroulante **Sélectionner un format**. Les formats suivants sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="37d16-p108">The Monitoring Reports provide at least two different ways to export the data included in a report. You can use the **Export** option in the toolbar that appears at the top of each report. To use this option, select the desired export format from the **Select a format** drop-down list. The following formats are available to you:</span></span>

  - <span data-ttu-id="37d16-149">fichier XML avec données de rapport ;</span><span class="sxs-lookup"><span data-stu-id="37d16-149">XML file with report data</span></span>

  - <span data-ttu-id="37d16-150">fichier CSV (valeurs séparées par des virgules) ;</span><span class="sxs-lookup"><span data-stu-id="37d16-150">CSV (comma delimited)</span></span>

  - <span data-ttu-id="37d16-151">fichier Acrobat (PDF) ;</span><span class="sxs-lookup"><span data-stu-id="37d16-151">Acrobat (PDF) file</span></span>

  - <span data-ttu-id="37d16-152">fichier MHTML (archive Web) ;</span><span class="sxs-lookup"><span data-stu-id="37d16-152">MHTML (web archive)</span></span>

  - <span data-ttu-id="37d16-153">fichier Excel ;</span><span class="sxs-lookup"><span data-stu-id="37d16-153">Excel</span></span>

  - <span data-ttu-id="37d16-154">fichier TIFF ;</span><span class="sxs-lookup"><span data-stu-id="37d16-154">TIFF file</span></span>

  - <span data-ttu-id="37d16-155">fichier Word.</span><span class="sxs-lookup"><span data-stu-id="37d16-155">Word</span></span>

<span data-ttu-id="37d16-p109">Après avoir sélectionné un format, cliquez sur **Exporter**. Lorsque la boîte de dialogue **Téléchargement de fichier** s’affiche, cliquez sur **Enregistrer**. Dans la boîte de dialogue **Enregistrer sous**, sélectionnez un dossier de destination, entrez un nom de fichier, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="37d16-p109">After selecting a format, click **Export**. When the **File Download** dialog box appears, click **Save**. In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>

<span data-ttu-id="37d16-p110">Si Microsoft OneNote est installé, vous pouvez également copier les données de rapport dans OneNote. Pour cela, cliquez avec le bouton droit sur le bouton **Afficher le rapport** dans la barre d’outils. Dans la boîte de dialogue **Sélectionner un emplacement dans OneNote**, sélectionnez dans OneNote la section où vous souhaitez copier les données, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="37d16-p110">If you have Microsoft OneNote installed, you can also copy the report data to OneNote. To do this, right-click the **View Report** button on the toolbar. In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

