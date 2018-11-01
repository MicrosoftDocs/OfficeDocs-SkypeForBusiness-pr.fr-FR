---
title: Utilisation du tableau de bord de suivi dans Lync Server 2013
TOCTitle: Utilisation du tableau de bord de suivi dans Lync Server 2013
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49891571
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation du tableau de bord de suivi dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-02-05_

Le Tableau de bord de suivi fournit aux administrateurs un rapide aperçu de l’intégrité et de l’utilisation du système Microsoft Lync Server 2013. Le tableau de bord est conçu pour afficher une vue agrégée des mesures système clés, et ce en affichant soit :

  - Les totaux du jour. Notez que les valeurs affichées pour le jour actuel représentent les données enregistrées de minuit à l’heure actuelle (sur la base de l’heure locale du serveur de rapports). Par conséquent, vous ne verrez que les données d’un jour partiel et non d’une période de 24 heures. Par exemple, si l’heure locale du serveur est 8:00, les données sur huit heures sont affichées, correspondant à la durée entre minuit et l’heure actuelle.

  - Les totaux de la semaine, et les totaux de la tendance des six semaines précédentes.

  - Les totaux du mois, et les totaux de la tendance des six mois précédents (pour l’utilisation du système uniquement).

Notez que vous pouvez utiliser l'applet de commande [Get-CsReportingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsReportingConfiguration) pour retourner l'URL utilisée pour accéder aux rapports de surveillance de Lync Server 2013 :

    Get-CsReportingConfiguration

Par défaut, le Tableau de bord de suivi affiche les données des mesures suivantes pour la semaine en cours (et les totaux de la tendance des six semaines précédentes) :

## Mesures d’utilisation du système

**Enregistrement**

  - Ouvertures de sessions à utilisateur unique

**Égal à égal**

  - Nombre total de sessions

  - Sessions de messagerie instantanée

  - Sessions audio

  - Sessions vidéo

  - Partage d’application

  - Nombre total de minutes de session audio

  - Nombre moyen de minutes de session audio

**Conférence**

  - Nombre total de conférences

  - Conférences par messagerie instantanée

  - Conférences A/V

  - Conférences de partage d’application

  - Conférences web

  - Nombre total d’organisateurs

  - Nombre total de minutes par conférence A/V

  - Nombre moyen de minutes par conférence A/V

  - Nombre total de conférences PSTN

  - Nombre total de participants PSTN

  - Nombre total de minutes par participant PSTN

Outre les mesures d’utilisation du système, les mesures suivantes indiquent le total pour le jour actuel et les six jours précédents (si vous sélectionnez **Vue hebdomadaire**), ou pour la semaine en cours et les six semaines précédentes si vous sélectionnez **Vue mensuelle**.

## Diagnostics des appels par utilisateur

**Utilisateurs ayant rencontré des problèmes d’appel**

  - Nombre total d’utilisateurs ayant rencontré des problèmes d’appel

  - Organisateurs de conférence ayant rencontré des problèmes d’appel

**Utilisateurs ayant eu des appels de qualité médiocre**

  - Nombre total d’utilisateurs ayant eu des appels de qualité médiocre

## Diagnostics des appels

Égal à égal

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

Cinq principaux serveurs par session ayant échoué

## Diagnostic de la qualité des médias

Égal à égal

  - Nombre total d’appels de qualité médiocre

  - Pourcentage d’appels de qualité médiocre

  - Appels PSTN de qualité médiocre

Conférence

  - Nombre total d’appels de qualité médiocre

  - Pourcentage d’appels de qualité médiocre

  - Appels PSTN de qualité médiocre

Cinq derniers serveurs par pourcentage d’appels de qualité médiocre

## Travail avec le Tableau de bord de suivi

Comme mentionné plus haut, les totaux par défaut sont affichés pour la semaine en cours et les valeurs de tendance pour les six semaines précédentes. Si vous préférez voir les totaux pour le mois en cours (ainsi que les valeurs de la tendance sur les six mois précédents), cliquez sur le lien **Vue mensuelle** dans le coin supérieur droit du tableau de bord. Si vous décidez d’afficher les totaux mensuels, le texte du lien devient **Vue hebdomadaire**. Vous pouvez revenir à la vue mensuelle en cliquant dessus.

> [!TIP]  
> Le Tableau de bord de suivi ne vous permet que de voir les totaux de la semaine (ou du mois) en cours et les valeurs de tendance des six semaines précédentes (ou mois précédents). Vous ne pouvez pas modifier ces dates et périodes. Par exemple, le tableau de bord ne vous permet pas de voir les totaux des rapports pour la période commençant neuf mois plus tôt.

Les valeurs affichées dans les colonnes **Cette semaine**, **Ce mois-ci** ou **Aujourd’hui** vous mènent à des informations détaillées sur l’élément. Rappelez-vous que le nom de la colonne et les valeurs qui y sont affichées changent en fonction de la mesure choisie et de votre choix de la vue hebdomadaire ou mensuelle. Par exemple, si vous cliquez sur les totaux affichés pour la mesure **Ouvertures de sessions à utilisateur unique**, vous verrez le **Rapport d’enregistrement de l’utilisateur** pour la période spécifiée. Vous pouvez retourner au Tableau de bord de suivi à tout moment en cliquant sur **Tableau de bord**.

> [!TIP]  
> Vous pouvez également accéder à la page d’accueil des rapports serveur de surveillance en cliquant sur le lien <strong>Rapports</strong> dans le coin supérieur droit du tableau de bord.

La colonne **Tendance** montre un graphique en courbes indiquant les totaux des six semaines précédentes (ou, selon la mesure et l’intervalle de temps, les six derniers jours ou mois). Ces graphiques en courbes affichent un point de données sans nom pour chaque période (par exemple, un point de données sans nom pour chacune des six semaines précédentes). Cependant, vous pouvez récupérer les valeurs réelles pour ces graphiques en maintenant le pointeur de la souris sur le graphique. Une info-bulle vous indique alors les valeurs minimale et maximale du graphique.

## Exportation de données à partir du Tableau de bord de suivi

Le Tableau de bord de suivi permet d’exporter la vue en cours de différentes manières. Dans la barre d’outils du tableau de bord se trouve une icône représentant une disquette avec une flèche verte attachée. Si vous cliquez dessus, une liste déroulante avec les formats d’exportation de données suivants apparaît :

  - fichier XML avec données de rapport ;

  - fichier CSV (valeurs séparées par des virgules) ;

  - fichier PDF ;

  - fichier MHTML (archive Web) ;

  - fichier Excel ;

  - fichier TIFF ;

  - fichier Word.

Pour exporter la vue active du tableau de bord (et ses valeurs), cliquez sur l’option d’exportation souhaitée. Lync Server 2013 génère un rapport au format spécifié et vous donne le choix entre ouvrir ce rapport ou l’enregistrer. Notez que Lync Server intitule le rapport **Tableau de bord de suivi** par défaut et l’enregistre dans votre dossier Téléchargements. Pour nommer le rapport différemment ou pour le stocker dans un autre dossier, cliquez sur la flèche située à côté du bouton **Enregistrer**, puis cliquez sur **Enregistrer sous**. Si le nom **Tableau de bord de suivi** et le dossier d’enregistrement Téléchargements vous conviennent, vous pouvez simplement appuyer sur le bouton **Enregistrer**.

Lorsque vous essayez d’exporter des données du tableau de bord, il est possible qu’une boîte de dialogue **Alerte de sécurité** apparaisse avec le message « Vos paramètres actuels ne permettent pas le téléchargement de ce fichier. » Dans ce cas, procédez comme suit :

  - Dans Internet Explorer, sélectionnez **Options Internet**.

  - Dans la boîte de dialogue **Options Internet**, sous l’onglet **Sécurité**, cliquez sur **Sites approuvés**, puis sur **Sites**.

  - Dans la boîte de dialogue **Sites approuvés**, cliquez sur **Ajouter** pour ajouter le Lync Server 2013 qui exécute les rapports Lync Server 2013 aux collection de sites web approuvés.

  - Cliquez sur **Fermer**, puis sur **OK**.

Vous devez ensuite actualiser le Tableau de bord de suivi pour que les modifications prennent effet. Pour cela, appuyez sur F5 ou cliquez sur l’icône **Actualiser** de la barre d’outils du tableau de bord. (L’icône **Actualiser** représente un cercle contenant deux flèches vertes.)

Vous pouvez également créer une feuille de calcul Excel avec les flux de données actives, comprenant des liens vers les dernières données du Tableau de bord de suivi. Pour créer un fichier de flux de données actives, cliquez sur l’icône orange **Exporter vers un flux de données** dans la barre d’outils.

Si vous préférez imprimer le tableau de bord actif, cliquez sur l’icône d’imprimante située dans la barre d’outils.

