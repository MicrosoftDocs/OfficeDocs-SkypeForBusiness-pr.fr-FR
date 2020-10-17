---
title: 'Lync Server 2013 : utilisation du tableau de bord de suivi'
description: 'Lync Server 2013 : utilisation du tableau de bord de suivi.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8a68fa1e55b7d0b8305c53802ddabaa904fa214
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556040"
---
# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a>Utilisation du tableau de bord de suivi dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-05_

Le tableau de bord de suivi fournit aux administrateurs une vue d’ensemble rapide de l’État et de l’utilisation du système de Microsoft Lync Server 2013. Le tableau de bord est conçu pour afficher une vue agrégée des mesures système clés et pour ce faire en affichant soit :

  - Totaux du jour actuel. Notez que les valeurs affichées pour le jour actuel représentent des données qui ont été enregistrées de minuit à l’heure actuelle (en fonction de l’heure locale du serveur de rapports). Cela signifie que vous allez généralement consulter les données d’une journée partielle et non pendant une période de 24 heures. Par exemple, si l’heure locale du serveur est 8:00 AM, vous pouvez voir huit heures de données, car il y a huit heures entre minuit et l’heure actuelle de 8:00 AM.

  - Les totaux de la semaine, et les totaux de la tendance des six semaines précédentes.

  - Les totaux du mois, et les totaux de la tendance des six mois précédents (pour l’utilisation du système uniquement).

Notez que vous pouvez utiliser la cmdlet [Get-applet csreportingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) pour renvoyer l’URL utilisée pour accéder aux rapports de surveillance Lync Server 2013 :

    Get-CsReportingConfiguration

Par défaut, le tableau de bord de suivi affiche les données des mesures suivantes pour la semaine en cours (et les totaux de la tendance des six semaines précédentes) :

<div>

## <a name="system-usage-metrics"></a>Mesures d’utilisation du système

**Registration**

  - Ouvertures de session utilisateur uniques

**Pair à pair**

  - Nombre total de sessions

  - Sessions de messagerie instantanée

  - Sessions audio

  - Sessions vidéo

  - Partage d'application

  - Nombre total de minutes de session audio

  - Nombre moyen de minutes par session audio

**Conférence**

  - Nombre total de conférences

  - Conférences de messagerie instantanée

  - Conférences A/V

  - Conférences de partage d’application

  - Conférences Web

  - Nombre total de organisateurs

  - Nombre total de minutes par conférence A/V

  - Nbre. Minutes de conférence A/V

  - Nombre total de conférences PSTN

  - Nombre total de participants PSTN

  - Nombre total de minutes par participant PSTN

Outre les mesures d’utilisation du système, les mesures suivantes affichent le total du jour actuel et des six jours précédents (si vous sélectionnez **affichage hebdomadaire**) ou pour la semaine en cours et les six dernières semaines si vous sélectionnez **affichage mensuel**.

</div>

<div>

## <a name="per-user-call-diagnostics"></a>Diagnostics des appels de Per-User

**Utilisateurs avec des échecs d’appel**

  - Nombre total d’utilisateurs avec des échecs d’appel

  - Organisateurs de conférence avec des échecs d’appel

**Utilisateurs avec des appels de qualité médiocre**

  - Nombre total d’utilisateurs avec des appels de qualité médiocre

</div>

<div>

## <a name="call-diagnostics"></a>Diagnostics des appels

Pair à pair

  - Nombre total d’échecs

  - Taux d’échec global

  - Taux d’échec de la messagerie instantanée

  - Taux d’échec audio

  - Taux d’échec du partage d’application

Conférence

  - Nombre total d’échecs

  - Taux d’échec global

  - Taux d’échec de la messagerie instantanée

  - Taux d’échec A/V

  - Taux d’échec du partage d’application

Cinq principaux serveurs par sessions ayant échoué

</div>

<div>

## <a name="media-quality-diagnostics"></a>Diagnostic de la qualité des médias

Pair à pair

  - Nombre total d’appels de qualité médiocre

  - Pourcentage d’appels de qualité médiocre

  - Appels RTC avec une qualité médiocre

Conférence

  - Nombre total d’appels de qualité médiocre

  - Pourcentage d’appels de qualité médiocre

  - Appels RTC avec une qualité médiocre

Serveurs les plus défavorables par pourcentage d’appels de qualité médiocre

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a>Utilisation du tableau de bord de suivi

Comme indiqué plus haut, par défaut, les totaux sont affichés pour la semaine en cours et les valeurs de tendance sont affichées pour les six semaines précédentes. Si vous préférez afficher les totaux pour le mois en cours (ainsi que les valeurs de tendance pour les six derniers mois), cliquez sur le lien **affichage mensuel** dans le coin supérieur droit du tableau de bord. Si vous décidez d’afficher les totaux mensuels, le texte du lien prend la forme **affichage hebdomadaire**. Vous pouvez revenir à la vue hebdomadaire en cliquant sur ce lien.

<div>


> [!TIP]  
> Le tableau de bord de suivi vous limite à consulter les totaux de la semaine (ou du mois) en cours et les valeurs de tendance pour les six semaines (ou les mois précédents). Vous ne pouvez pas modifier ces dates et heures. Par exemple, vous ne pouvez pas utiliser le tableau de bord pour afficher les totaux du rapport pour la période commençant neuf mois plus tôt.



</div>

Les valeurs affichées dans les colonnes **cette semaine**, **ce mois**-ci ou **aujourd’hui** vous permettent d’accéder à des informations plus détaillées sur l’élément. N’oubliez pas que le nom de la colonne et les valeurs affichées dans cette colonne diffèrent souvent en fonction de la mesure choisie et selon que vous avez sélectionné la vue hebdomadaire ou mensuelle. Par exemple, si vous cliquez sur les totaux affichés pour la mesure **ouvertures de session utilisateur uniques** , le **rapport d’enregistrement** de l’utilisateur s’affiche pour la période spécifiée. Vous pouvez revenir au tableau de bord de suivi à tout moment en cliquant sur **tableau de bord**.

<div>


> [!TIP]  
> Vous pouvez également accéder à la page d’accueil des rapports du serveur de surveillance en cliquant sur le lien <STRONG>rapports</STRONG> dans le coin supérieur droit du tableau de bord.



</div>

La colonne **tendance** affiche un graphique linéaire qui indique les totaux des six dernières semaines (ou, en fonction de la mesure et de l’intervalle de temps, des six derniers jours ou des six derniers mois). Ces graphiques linéaires affichent un point de données sans nom pour chaque période (par exemple, un point de données sans nom pour chacune des six semaines précédentes). Toutefois, vous pouvez récupérer les valeurs réelles de ces graphiques en maintenant le pointeur de la souris sur le graphique. Dans ce cas, une info-bulle vous indique les valeurs maximale et minimale dans le graphique.

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a>Exportation de données à partir du tableau de bord de suivi

Le tableau de bord de suivi offre plusieurs méthodes pour exporter l’affichage actuel du tableau de bord. Dans la barre d’outils Tableau de bord, une icône ressemblant à une disquette avec une flèche verte s’affiche. Si vous cliquez sur cette icône, une liste déroulante s’affiche pour vous donner les formats d’exportation de données suivants :

  - fichier XML avec données de rapport ;

  - fichier CSV (valeurs séparées par des virgules) ;

  - PDF

  - fichier MHTML (archive web) ;

  - Excel

  - fichier TIFF ;

  - Word

Pour exporter l’affichage actuel du tableau de bord (et ses valeurs), cliquez sur l’option d’exportation souhaitée. Lync Server 2013 génère un rapport au format spécifié, puis vous offre la possibilité d’ouvrir ce rapport ou de l’enregistrer. Notez que, par défaut, Lync Server titres le **tableau de bord de suivi** des rapports et l’enregistre dans votre dossier téléchargements. Pour donner un nom différent à l’État ou pour le stocker dans un autre dossier, cliquez sur la flèche en regard du bouton **Enregistrer** , puis cliquez sur **Enregistrer sous**. Si le tableau de bord de **suivi** des noms est correct et que le rapport est enregistré dans le dossier downloads, vous pouvez simplement cliquer sur le bouton **Enregistrer** .

Il est possible que, lorsque vous essayez d’exporter des données de tableau de bord, une boîte de dialogue **alerte de sécurité** s’affiche en même temps que le message « vos paramètres actuels n’autorisent pas le téléchargement de ce fichier. » Dans ce cas, procédez comme suit :

  - Dans Internet Explorer, sélectionnez **Options Internet**.

  - Dans la boîte de dialogue **Options Internet** , sous l’onglet **sécurité** , cliquez sur **sites de confiance** , puis sur **sites**.

  - Dans la boîte de dialogue **sites de confiance** , cliquez sur **Ajouter** pour ajouter le serveur Lync Server 2013 exécutant Lync Server 2013 rapports aux collections de sites Web de confiance.

  - Cliquez sur **Fermer** , puis sur **OK**.

Vous devrez ensuite actualiser le tableau de bord de suivi pour que les modifications prennent effet. Pour ce faire, appuyez sur F5 ou cliquez sur l’icône **Actualiser** de la barre d’outils Tableau de bord. (L’icône d' **actualisation** est un cercle avec une paire de flèches vertes.)

Vous pouvez également créer une feuille de calcul Excel qui inclut des flux de données dynamiques, qui inclut des liens vers les dernières données du tableau de bord de surveillance. Pour créer un fichier de flux de données actives, cliquez sur l’icône orange **Exporter vers un flux de données** dans la barre d’outils.

Si vous préférez imprimer le tableau de bord actif, cliquez sur l’icône de l’imprimante dans la barre d’outils.

</div>

</div>

<span> </span>

</div>

</div>

</div>

