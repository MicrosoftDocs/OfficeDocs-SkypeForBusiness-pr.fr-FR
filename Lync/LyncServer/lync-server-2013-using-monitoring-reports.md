---
title: 'Lync Server 2013 : Utilisation des rapports de surveillance'
TOCTitle: Utilisation des rapports de surveillance
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558662(v=OCS.15)
ms:contentKeyID: 49297713
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation des rapports de surveillance dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-21_

Lync Server 2013 inclut un ensemble de rapports standard publiés par Microsoft SQL Server Reporting Services. Ces rapports, accessibles via un navigateur web, fournissent des informations relatives à l’utilisation, des informations de diagnostic des appels, ainsi que des informations sur la qualité des médias, en fonction des enregistrements des détails des appels et des enregistrements de la qualité de l’expérience (QoE), stockés respectivement dans les bases de données d’enregistrement des détails des appels et QoE.

Pour pouvoir utiliser ces rapports, vous devez installer les rapports de surveillance sur un ordinateur qui exécute une instance de SQL Server.

## Dans cette section

  - [Utilisation du tableau de bord de suivi dans Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   Fournit aux administrateurs une vue d’ensemble rapide de l’intégrité et l’utilisation de leur système.

  - [Rapports d’utilisation système dans Lync Server 2013](lync-server-2013-system-usage-reports.md)   Fournit des informations d’utilisation système basées sur des données CDR recueillies par Lync Server.

  - [Rapports de diagnostic des appels (par utilisateur) dans Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   Fournit des informations spécifiques à chaque utilisateur concernant les sessions de conférence et les sessions P2P ayant échoué.

  - [Rapports de diagnostic des appels dans Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   Fournit des informations de synthèse et des données de diagnostic pour les sessions de conférence et les sessions P2P ayant échoué.

  - [Rapports de diagnostic de la qualité des médias dans Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   Fournit des informations sur la qualité des appels et des informations de diagnostic et d’identification et de résolution des problèmes pour les appels ayant échoué.

## Recherche d’enregistrements

Les rapports de surveillance affichent uniquement une quantité limitée d’enregistrements à l’écran. La quantité réelle d’enregistrements affichés sur un écran dépend du rapport. Pour visualiser les enregistrements qui ne sont pas affichés actuellement à l’écran, vous pouvez utiliser les contrôles standard « Précédent » et « Suivant » (qui se trouvent dans la barre d’outils de chaque rapport) qui vous permettent de parcourir les données. Vous pouvez également accéder rapidement à la première ou dernière page du jeu de données.

Outre ces contrôles, vous pouvez accéder à une page quelconque du jeu de données en tapant simplement son numéro dans la zone **Page actuelle**, puis en appuyant sur Entrée.

Chaque rapport offre également une possibilité limitée de rechercher des enregistrements. Pour rechercher des enregistrements sur la base d’une valeur donnée, tapez cette valeur dans la zone **Rechercher**, puis cliquez sur **Rechercher**. Le rapport commence à explorer les données et s’arrête sur la première instance de la valeur que vous avez entrée dans la zone **Rechercher**. Pour trouver l’enregistrement suivant qui répond aux critères de recherche, cliquez sur **Suivant**.

Comme mentionné plus haut, les rapports de surveillance procurent uniquement des fonctionnalités de recherche de base. Par exemple, vous ne pouvez pas spécifier le champ dans lequel rechercher la valeur. Le mécanisme de recherche recherche des valeurs correspondantes dans chaque champ de chaque enregistrement. Vous ne pouvez pas utiliser de caractères génériques dans vos recherches et toutes les recherches tentent de trouver des valeurs partielles. Cela signifie que si vous recherchez 111, la recherche renvoie la valeur 111, ainsi que les valeurs 11100, 811, 3112, 611A5B et tout autre champ qui comprend la valeur 111 n’importe où.

Chaque rapport est configuré de façon à afficher un ensemble d’enregistrements par défaut. Par exemple, par défaut le rapport Enregistrement d’utilisateur montre les activités d’enregistrement des utilisateurs pour la semaine passée. Dans certains cas, il se peut que le rapport soit vide, ce qui signifie que aucun enregistrement utilisateur n’a eu lieu durant la semaine passée. Si le message « Aucun résultat ne correspond aux filtres du rapport » s’affiche, essayez de modifier les valeurs de filtre (par exemple, sélectionnez le moi dernier plutôt que la semaine dernière comme période) et réexécutez la requête. Pour plus d’informations, reportez-vous à la section « Filtrage des données » dans la suite de cette rubrique.

## Filtrage des données

Il se peut parfois que vous souhaitiez examiner uniquement un sous-ensemble d’enregistrements, par exemple, les sessions P2P plutôt que les sessions de conférence ET P2P. De même, il se peut que vous deviez réduire le nombre d’enregistrements renvoyés. Par défaut, un rapport ne peut afficher que les 1000 premiers enregistrements d’un jeu de données. Pour faire face à ces cas de figure, la plupart des rapports proposent plusieurs options de filtrage. Par exemple, si vous souhaitez afficher uniquement les enregistrements compris entre le 1er janvier 2011 et le 15 janvier 2011, vous pouvez entrer la date du 1er janvier 2011 dans la zone **De** et la date du 15 janvier 2011 dans la zone **À**. Si vous cliquez ensuite sur **Afficher le rapport**, les données renvoyées se limitent aux activités ayant eu lieu entre le 1er et le 15 janvier 2011.

Les filtres à votre disposition dépendent du rapport que vous visualisez. Pour plus d’informations sur un rapport spécifique, reportez-vous à la rubrique d’aide relative à ce rapport.

## Exportation de données

Les rapports de surveillance fournissent au moins deux manières différentes d’exporter les données incluses dans un rapport. Vous pouvez utiliser l’option **Exporter** de la barre d’outils affichée en haut de chaque rapport. Pour utiliser cette option, sélectionnez le format d’exportation souhaité dans la liste déroulante **Sélectionner un format**. Les formats suivants sont disponibles :

  - fichier XML avec données de rapport ;

  - fichier CSV (valeurs séparées par des virgules) ;

  - fichier Acrobat (PDF) ;

  - fichier MHTML (archive Web) ;

  - fichier Excel ;

  - fichier TIFF ;

  - fichier Word.

Après avoir sélectionné un format, cliquez sur **Exporter**. Lorsque la boîte de dialogue **Téléchargement de fichier** s’affiche, cliquez sur **Enregistrer**. Dans la boîte de dialogue **Enregistrer sous**, sélectionnez un dossier de destination, entrez un nom de fichier, puis cliquez sur **Enregistrer**.

Si Microsoft OneNote est installé, vous pouvez également copier les données de rapport dans OneNote. Pour cela, cliquez avec le bouton droit sur le bouton **Afficher le rapport** dans la barre d’outils. Dans la boîte de dialogue **Sélectionner un emplacement dans OneNote**, sélectionnez dans OneNote la section où vous souhaitez copier les données, puis cliquez sur **OK**.

