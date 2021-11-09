---
title: Utilisation du tableau de bord de surveillance dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Résumé : Découvrez le tableau de bord de surveillance dans Skype Entreprise Server.'
ms.openlocfilehash: ac68ae2174fcd7c4266da77c2d079c2f9a31d8e5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862301"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a>Utilisation du tableau de bord de surveillance dans Skype Entreprise Server
 
**Résumé :** Découvrez le tableau de bord de surveillance dans Skype Entreprise Server.
  
Le Tableau de bord de surveillance offre aux administrateurs une vue d’ensemble rapide de leur Skype Entreprise Server et de l’utilisation du système. Le tableau de bord est conçu pour afficher une vue agrégée des mesures système clés et pour ce faire, en affichant :
  
- Totaux du jour en cours. Notez que les valeurs affichées pour le jour actuel représentent des données enregistrées de minuit à l’heure actuelle (en fonction de l’heure locale du serveur de rapports). Cela signifie que vous affichez généralement les données pour un jour partiel et non pour une période de 24 heures. Par exemple, si l’heure locale du serveur est 8:00 AM, vous voyez une valeur de huit heures de données, car il y a huit heures entre minuit et l’heure actuelle de 8:00.
    
- Totaux de la semaine et totaux de tendance pour les six semaines précédentes.
    
- Les totaux du mois et les totaux de tendance des six derniers mois (pour l’utilisation du système uniquement).
    
Notez que vous pouvez utiliser l’cmdlet [Get-CsReportingConfiguration](/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) pour renvoyer l’URL utilisée pour accéder Skype Entreprise Server rapports de surveillance :
  
```PowerShell
Get-CsReportingConfiguration
```

Par défaut, le Tableau de bord de surveillance affiche les données pour les mesures suivantes pour la semaine en cours (et les totaux de tendance pour les six semaines précédentes) :
  
## <a name="system-usage-metrics"></a>Mesures d’utilisation du système

 **Registration**
  
- Connexions utilisateur uniques
    
  **Pair à pair**
  
- Nombre total de sessions
    
- Sessions de messagerie instantanée
    
- Sessions audio
    
- Sessions vidéo
    
- Partage d'application
    
- Nombre total de minutes par session audio
    
- Avg. minutes de session audio
    
  **Conférence**
  
- Nombre total de conférences
    
- Conférences par messagerie instantanée
    
- Conférences A/V
    
- Conférences de partage d’application
    
- Conférences web
    
- Nombre total d’organisateurs
    
- Nombre total de minutes par conférence A/V
    
- Avg. Minutes de conférence A/V
    
- Nombre total de conférences PSTN
    
- Nombre total de participants PSTN
    
- Nombre total de minutes par participant PSTN
    
Outre les mesures Utilisation du système, les mesures suivantes affichent le total pour le jour actuel et les six jours précédents (si vous sélectionnez Affichage **hebdomadaire)** ou pour la semaine en cours et les six semaines passées si vous sélectionnez Affichage **mensuel.**
  
## <a name="per-user-call-diagnostics"></a>Per-User diagnostics des appels

 **Utilisateurs avec des échecs d’appel**
  
- Nombre total d’utilisateurs ayant échoué aux appels
    
- Organisateurs de conférence avec des échecs d’appel
    
  **Utilisateurs ayant des appels de qualité médiocre**
  
- Nombre total d’utilisateurs ayant des appels de qualité médiocre
    
## <a name="call-diagnostics"></a>Diagnostics des appels

Pair à pair
  
- Nombre total d’échecs
    
- Taux d’échec global
    
- Taux d’échec de messagerie instantanée
    
- Taux d’échec audio
    
- Taux d’échec du partage d’application
    
Programme
  
- Nombre total d’échecs
    
- Taux d’échec global
    
- Taux d’échec de messagerie instantanée
    
- Taux d’échec A/V
    
- Taux d’échec du partage d’application
    
Cinq serveurs principaux en cas d’échec des sessions
  
## <a name="media-quality-diagnostics"></a>Diagnostics de la qualité des médias

Pair à pair
  
- Nombre total d’appels de qualité médiocre
    
- Pourcentage d’appels de qualité médiocre
    
- Appels PSTN de qualité médiocre
    
Programme
  
- Nombre total d’appels de qualité médiocre
    
- Pourcentage d’appels de qualité médiocre
    
- Appels PSTN de qualité médiocre
    
Principaux serveurs par pourcentage d’appels de qualité médiocre
  
## <a name="working-with-the-monitoring-dashboard"></a>Travailler avec le Tableau de bord de surveillance

Comme indiqué, les totaux par défaut sont affichés pour la semaine en cours et les valeurs de tendance sont affichées pour les six semaines précédentes. Si vous préférez afficher les totaux du mois en cours (ainsi que  les valeurs de tendance des six derniers mois), cliquez sur le lien Affichage mensuel dans le coin supérieur droit du tableau de bord. Si vous décidez d’afficher les totaux mensuels, le texte du lien sera changé en **Affichage hebdomadaire.** Vous pouvez revenir à l’affichage hebdomadaire en cliquant sur ce lien.
  
> [!TIP]
> Le Tableau de bord de surveillance vous limite à la recherche des totaux de la semaine (ou du mois) en cours et des valeurs de tendance des six semaines (ou mois précédents). Vous ne pouvez pas modifier ces dates et heures. Par exemple, vous ne pouvez pas utiliser le tableau de bord pour afficher les totaux des rapports pour la période commençant à neuf mois. 
  
Les valeurs affichées dans les  colonnes **Cette semaine,** **Ce mois** ou Aujourd’hui vous relient à des informations plus détaillées sur l’élément. N’oubliez pas que le nom de colonne et les valeurs affichées dans cette colonne varient souvent en fonction de la mesure choisie et selon que vous avez sélectionné un affichage hebdomadaire ou mensuel. Par exemple, si vous cliquez sur les totaux affichés  pour la mesure Ouvertures de session utilisateur **uniques,** vous verrez le rapport d’enregistrement de l’utilisateur pour la période spécifiée. Vous pouvez revenir au Tableau de bord de surveillance à tout moment en cliquant sur **Tableau de bord.**
  
> [!TIP]
> Vous pouvez également accéder à la page d’accueil Rapports du serveur de surveillance en cliquant sur le lien **Rapports** dans le coin supérieur droit du tableau de bord.
  
La  colonne Tendance affiche un graphique en courbes simple qui affiche les totaux des six semaines précédentes (ou, en fonction de la mesure et de l’intervalle de temps, des six derniers jours ou des six derniers mois). Ces graphiques en courbes simples affichent un point de données non ajouté pour chaque période (par exemple, un point de données non ajouté pour chacune des six semaines précédentes). Toutefois, vous pouvez récupérer les valeurs réelles de ces graphiques en maintenant le pointeur de la souris sur le graphique. Dans ce cas, une info-conseil vous indique les valeurs maximale et minimale du graphique.
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a>Exportation de données à partir du tableau de bord de surveillance

Le Tableau de bord de surveillance fournit plusieurs façons d’exporter l’affichage actuel du tableau de bord. Dans la barre d’outils du tableau de bord, vous verrez une icône qui ressemble à une disquette avec une flèche verte attachée à celle-ci. Si vous cliquez sur cette icône, une liste dropdown s’affiche pour vous donner les formats d’exportation de données suivants :
  
- fichier XML avec données de rapport ;
    
- fichier CSV (valeurs séparées par des virgules) ;
    
- PDF
    
- fichier MHTML (archive web) ;
    
- Excel
    
- fichier TIFF ;
    
- Word
    
Pour exporter l’affichage actuel du tableau de bord (et ses valeurs), cliquez sur l’option d’exportation souhaitée. Skype Entreprise Server génère un rapport dans le format spécifié, puis vous offre la possibilité d’ouvrir ce rapport ou de l’enregistrer. Notez que, par défaut, Skype Entreprise Server  le tableau de bord de surveillance du rapport et l’enregistre dans votre dossier Téléchargements. Pour donner un nom différent au rapport ou pour le stocker  dans un autre dossier, cliquez sur la flèche en face du bouton Enregistrer, puis cliquez sur **Enregistrer sous**. Si vous avez  bien le nom Tableau de bord de surveillance et que le rapport est enregistré dans le dossier Téléchargements, vous pouvez simplement cliquer sur **le bouton** Enregistrer.
  
Il est possible que, lorsque vous essayez  d’exporter des données de tableau de bord, une boîte de dialogue Alerte de sécurité s’affiche avec le message « Vos paramètres actuels n’autorisent pas le téléchargement de ce fichier ». Si cela se produit, faites les choses suivantes :
  
- Dans Internet Explorer, sélectionnez **Options Internet.**
    
- Dans la boîte **de dialogue Options Internet,** sous l’onglet **Sécurité,** cliquez sur **Sites** de confiance, puis sur **Sites**.
    
- Dans la **boîte de**  dialogue Sites de confiance, cliquez sur Ajouter pour ajouter le Skype Entreprise Server qui Skype Entreprise Server rapports aux collections de sites web de confiance.
    
- Cliquez **sur Fermer,** puis sur **OK.**
    
Vous devrez ensuite actualiser le tableau de bord de surveillance avant que les modifications prennent effet. Pour ce faire, appuyez sur F5 ou cliquez sur **l’icône Actualiser** dans la barre d’outils tableau de bord. **(L’icône Actualiser** est un cercle avec une paire de flèches vertes.)
  
Vous pouvez également créer une feuille de calcul Excel qui inclut des flux de données en direct, qui inclut des liens vers les dernières données du Tableau de bord de surveillance. Pour créer un fichier de flux  de données en direct, cliquez sur l’icône orange Exporter vers le flux de données dans la barre d’outils.
  
Si vous préférez imprimer le tableau de bord actuel, cliquez sur l’icône de l’imprimante dans la barre d’outils.
