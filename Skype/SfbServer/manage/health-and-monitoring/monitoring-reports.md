---
title: Utilisation des rapports de surveillance dans Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
description: 'Résumé : Découvrez les rapports de surveillance dans Skype Entreprise Server.'
---

# <a name="using-monitoring-reports-in-skype-for-business-server"></a>Utilisation des rapports de surveillance dans Skype Entreprise Server 
 
**Résumé :** Découvrez les rapports de surveillance dans Skype Entreprise Server.
  
Skype Entreprise Server inclut un ensemble de rapports standard publiés par Microsoft SQL Server Reporting Service. Ces rapports, accessibles avec un navigateur web, fournissent des informations d’utilisation, de diagnostic d’appel et de qualité du média basées sur les enregistrements CDR (Enregistrement des détails des appels) et les enregistrements QoE (qualité de l’expérience) qui sont stockés dans les bases de données CDR et QoE.
  
Pour utiliser ces rapports, vous devez installer les rapports de surveillance sur un ordinateur qui exécute une instance du SQL Server.
  
## <a name="in-this-section"></a>Dans cette section

- [L’utilisation du Tableau de bord de Skype Entreprise Server](monitoring-dashboard.md) fournit aux administrateurs une vue d’ensemble rapide de l’état et de l’utilisation du système.
    
- [Les rapports d’utilisation du système Skype Entreprise Server](system-usage-reports.md) fournissent des informations d’utilisation système basées sur les données d’Skype Entreprise Server.
    
- [Rapports de diagnostic des appels (par utilisateur) dans Skype Entreprise Server](call-diagnostic-reports-per-user.md) fournit des informations par utilisateur sur les sessions d’égal à égal et de conférence qui ont échoué.
    
- [Call Diagnostic Reports in Skype Entreprise Server](call-diagnostic-reports.md) Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.
    
- [Media Quality Diagnostic Reports in Skype Entreprise Server](media-quality-diagnostic-reports.md) Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.
    
## <a name="locating-records"></a>Recherche d’enregistrements

Les rapports de surveillance affichent uniquement une quantité limitée d’enregistrements à l’écran. La quantité réelle d’enregistrements affichés sur un écran dépend du rapport. Pour afficher les enregistrements qui ne sont pas actuellement affichés à l’écran, vous pouvez utiliser les contrôles standard avant et arrière (disponibles dans la barre d’outils de chaque rapport) qui vous permettent de consulter les données. Vous pouvez également accéder rapidement à la première ou dernière page du jeu de données.
  
Outre ces contrôles, vous pouvez accéder à une page quelconque du jeu de données en tapant simplement son numéro dans la zone **Page actuelle**, puis en appuyant sur Entrée.
  
Chaque rapport offre également une possibilité limitée de rechercher des enregistrements. Pour rechercher des enregistrements sur la base d’une valeur donnée, tapez cette valeur dans la zone **Rechercher**, puis cliquez sur **Rechercher**. Le rapport commence à explorer les données et s’arrête sur la première instance de la valeur que vous avez entrée dans la zone **Rechercher**. Pour trouver l’enregistrement suivant qui répond aux critères de recherche, cliquez sur **Suivant**.
  
Comme mentionné plus haut, les rapports de surveillance procurent uniquement des fonctionnalités de recherche de base. Par exemple, vous ne pouvez pas spécifier le champ dans lequel rechercher la valeur. Le mécanisme de recherche recherche des valeurs correspondantes dans chaque champ de chaque enregistrement. Vous ne pouvez pas utiliser de caractères génériques dans vos recherches et toutes les recherches tentent de trouver des valeurs partielles. Cela signifie que si vous recherchez 111, la recherche renvoie la valeur 111, ainsi que les valeurs 11100, 811, 3112, 611A5B et tout autre champ qui comprend la valeur 111 n’importe où.
  
Chaque rapport est configuré pour afficher un jeu d’enregistrements par défaut. Par exemple, par défaut, le rapport d’enregistrement de l’utilisateur affiche les activités d’inscription des utilisateurs de la semaine précédente. Dans certains cas, cela peut entraîner un rapport qui ne renvoie aucun enregistrement. Dans ce cas, cela signifie qu’aucune inscription d’utilisateur n’a eu lieu au cours de la semaine précédente. Si le message « Aucun résultat ne correspond aux filtres de rapport », essayez de modifier les valeurs de filtre (par exemple, modifiez la période en mois passé plutôt que la semaine précédente) et réexécutez la requête. Pour plus d’informations, voir la section « Filtrage des données » plus loin dans cette rubrique.
  
## <a name="filtering-data"></a>Filtrage des données

Il se peut parfois que vous souhaitiez examiner uniquement un sous-ensemble d’enregistrements, par exemple les sessions d’égal à égal plutôt que les sessions de conférence ET d’égal à égal. De même, il se peut que vous deviez réduire le nombre d’enregistrements renvoyés. Par défaut, un rapport ne peut afficher que les 1000 premiers enregistrements d’un jeu de données. Pour faire face à ces cas de figure, la plupart des rapports proposent plusieurs options de filtrage. Par exemple, si vous souhaitez afficher uniquement les enregistrements compris entre le 1er janvier 2011 et le 15 janvier 2011, vous pouvez entrer la date du 1er janvier 2011 dans la zone **De** et la date du 15 janvier 2011 dans la zone **À**. Si vous cliquez ensuite sur **Afficher le rapport**, les données renvoyées se limitent aux activités ayant eu lieu entre le 1er et le 15 janvier 2011.
  
Les filtres à votre disposition dépendent du rapport que vous visualisez. Pour plus d’informations sur un rapport spécifique, voir la rubrique d’aide relative à ce rapport.
  
## <a name="exporting-data"></a>Exportation de données

Les rapports de surveillance fournissent au moins deux manières différentes d’exporter les données incluses dans un rapport. Vous pouvez utiliser l’option **Exporter** de la barre d’outils affichée en haut de chaque rapport. Pour utiliser cette option, sélectionnez le format d’exportation souhaité dans la liste déroulante **Sélectionner un format**. Les formats suivants sont disponibles :
  
- fichier XML avec données de rapport ;
    
- fichier CSV (valeurs séparées par des virgules) ;
    
- fichier Acrobat (PDF) ;
    
- fichier MHTML (archive web) ;
    
- Excel
    
- fichier TIFF ;
    
- Word
    
Après avoir sélectionné un format, cliquez sur **Exporter**. Lorsque la boîte de dialogue **Téléchargement de fichier** s’affiche, cliquez sur **Enregistrer**. Dans la boîte de dialogue **Enregistrer sous**, sélectionnez un dossier de destination, entrez un nom de fichier, puis cliquez sur **Enregistrer**.
  
Si Microsoft OneNote est installé, vous pouvez également copier les données de rapport dans OneNote. Pour cela, cliquez avec le bouton droit sur le bouton **Afficher le rapport** dans la barre d’outils. Dans la boîte de dialogue **Sélectionner un emplacement dans OneNote**, sélectionnez dans OneNote la section où vous souhaitez copier les données, puis cliquez sur **OK**.
  

