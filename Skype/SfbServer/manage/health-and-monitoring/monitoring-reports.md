---
title: Utilisation de rapports de surveillance dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
description: 'Résumé : Découvrez comment surveiller des rapports dans Skype entreprise Server.'
ms.openlocfilehash: 1468a012501753a720807f1b1ec609ff187ffc1c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817803"
---
# <a name="using-monitoring-reports-in-skype-for-business-server"></a>Utilisation de rapports de surveillance dans Skype entreprise Server 
 
**Résumé :** En savoir plus sur la surveillance des rapports dans Skype entreprise Server.
  
Skype entreprise Server inclut un ensemble de rapports standard publiés par le service Microsoft SQL Server Reporting. Ces rapports, accessibles avec un navigateur web, fournissent des informations d’utilisation, de diagnostic d’appel et de qualité du média basées sur les enregistrements CDR (Enregistrement des détails des appels) et les enregistrements QoE (qualité de l’expérience) qui sont stockés dans les bases de données CDR et QoE.
  
Pour utiliser ces rapports, vous devez installer des rapports d’analyse sur un ordinateur exécutant une instance de SQL Server.
  
## <a name="in-this-section"></a>Dans cette section

- [Utilisation du tableau de bord de surveillance dans Skype entreprise Server](monitoring-dashboard.md) Fournit aux administrateurs un aperçu rapide de l’intégrité du système et de l’utilisation du système.
    
- [Rapports sur l’utilisation du système dans Skype entreprise Server](system-usage-reports.md) Fournit des informations sur l’utilisation du système sur la base des données de CDR collectées par Skype entreprise Server.
    
- [Rapports de diagnostic des appels (par utilisateur) dans Skype entreprise Server](call-diagnostic-reports-per-user.md) Fournit des informations par utilisateur sur les sessions d’égal à égal et de conférence en échec.
    
- [Rapports de diagnostic des appels dans Skype entreprise Server](call-diagnostic-reports.md) Fournit des informations de synthèse et des données de diagnostic pour les sessions d’égal à égal et de conférence interrompues.
    
- [Rapports de diagnostic de qualité multimédia dans Skype entreprise Server](media-quality-diagnostic-reports.md) Fournit des informations sur la qualité d’appel ainsi que des informations de diagnostic et de dépannage pour les appels en échec.
    
## <a name="locating-records"></a>Recherche d’enregistrements

Les rapports de surveillance affichent uniquement une quantité limitée d’enregistrements à l’écran. La quantité réelle d’enregistrements affichés sur un écran dépend du rapport. Pour afficher les enregistrements qui ne sont pas visibles à l’écran, vous pouvez utiliser le contrôle suivant et précédent (qui se trouve sur la barre d’outils de chaque rapport) qui vous permet de parcourir les données. Vous pouvez également accéder rapidement à la première ou dernière page du jeu de données.
  
Outre ces contrôles, vous pouvez accéder à une page quelconque du jeu de données en tapant simplement son numéro dans la zone **Page actuelle**, puis en appuyant sur Entrée.
  
Chaque rapport offre également une possibilité limitée de rechercher des enregistrements. Pour rechercher des enregistrements sur la base d’une valeur donnée, tapez cette valeur dans la zone **Rechercher**, puis cliquez sur **Rechercher**. Le rapport commence à explorer les données et s’arrête sur la première instance de la valeur que vous avez entrée dans la zone **Rechercher**. Pour trouver l’enregistrement suivant qui répond aux critères de recherche, cliquez sur **Suivant**.
  
Comme mentionné plus haut, les rapports de surveillance procurent uniquement des fonctionnalités de recherche de base. Par exemple, vous ne pouvez pas spécifier le champ dans lequel rechercher la valeur. Le mécanisme de recherche des valeurs correspondantes dans chaque champ de chaque enregistrement. Vous ne pouvez pas utiliser de caractères génériques dans vos recherches et toutes les recherches tentent de trouver des valeurs partielles. Cela signifie que si vous recherchez 111, la recherche renvoie la valeur 111, ainsi que les valeurs 11100, 811, 3112, 611A5B et tout autre champ qui comprend la valeur 111 n’importe où.
  
Chaque rapport est configuré pour afficher un ensemble d’enregistrements par défaut. Par exemple, par défaut, le rapport sur l’inscription des utilisateurs présente les activités d’inscription des utilisateurs au cours de la semaine précédente. Dans certains cas, cela peut générer un État ne renvoyant aucun enregistrement. Le cas échéant, cela signifie qu’il n’y a pas eu d’inscriptions effectuées par les utilisateurs au cours de la semaine précédente. Si le message « aucune valeur ne correspond aux filtres du rapport » s’affiche, essayez de modifier les valeurs du filtre (par exemple, remplacez la période par le mois précédent plutôt que la semaine précédente) et réexécutez la requête. Pour plus d’informations, reportez-vous à la section « filtrage des données » plus loin dans cette rubrique.
  
## <a name="filtering-data"></a>Filtrage des données

Il se peut parfois que vous souhaitiez examiner uniquement un sous-ensemble d’enregistrements, par exemple, les sessions P2P plutôt que les sessions de conférence ET P2P. De même, il se peut que vous deviez réduire le nombre d’enregistrements renvoyés. Par défaut, un rapport ne peut afficher que les 1 000 premiers enregistrements d’un jeu de données. Pour faire face à ces cas de figure, la plupart des rapports proposent plusieurs options de filtrage. Par exemple, si vous souhaitez afficher uniquement les enregistrements compris entre le 1er janvier 2011 et le 15 janvier 2011, vous pouvez entrer la date du 1er janvier 2011 dans la zone **De** et la date du 15 janvier 2011 dans la zone **À**. Si vous cliquez ensuite sur **Afficher le rapport**, les données renvoyées se limitent aux activités ayant eu lieu entre le 1er et le 15 janvier 2011.
  
Les filtres à votre disposition dépendent du rapport que vous visualisez. Pour plus d’informations sur un rapport spécifique, reportez-vous à la rubrique d’aide relative à ce rapport.
  
## <a name="exporting-data"></a>Exportation de données

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
  

