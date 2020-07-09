---
title: Tableau de bord de qualité d’appel (bord) Forum aux questions (FAQ)
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Lisez le Forum aux questions et répondez aux questions sur le tableau de bord de qualité des appels de Microsoft Teams (bord).
ms.openlocfilehash: f33d66d9c8abb465c6680bacbbd2ff200cf930c6
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086170"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Tableau de bord de qualité d’appel (bord) Forum aux questions (FAQ)

## <a name="frequently-asked-questions"></a>Questions fréquemment posées

[Pourquoi bord marque-t-on comme bon dans le cas d’un ou plusieurs participants à la réunion ?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Pourquoi est-ce que je reçois une différence de 0,2% sur les mesures et le nombre d’utilisateurs et la façon d’obtenir des volumes plus précis ?](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Pourquoi les données du rapport bord v2 sont-elles différentes de celles du rapport bord v3 ?](#why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data)

[Pourquoi les données bord de Skype entreprise sont-elles différentes de celles bord de teams ?](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[Pourquoi ne puis-je pas voir EUII dans bord ?](#why-cant-i-see-euii-in-cqd)

[Pourquoi des informations Skype entreprise s’afficheront dans bord lorsque j’ai filtré uniquement pour les équipes ?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Pourquoi bord marque-t-on comme bon dans le cas d’un ou plusieurs participants à la réunion ?

Découvrez les règles utilisées par bord pour la [classification des flux](stream-classification-in-call-quality-dashboard.md).
 
Dans le cas des flux audio, l’un des cinq classifieurs, qui est calculé pour la moyenne en fonction de la longueur de l’appel, peut être un paramètre « Good ». Cela ne signifie pas que les utilisateurs n’ont pas eu d’action ayant contribué à une chute ou un problème audio. 

Pour savoir s’il s’agit d’un problème de réseau, observez le delta entre les valeurs moyennes de la session et les valeurs maximales. Les valeurs maximales sont le maximum détecté et signalé lors de la session.
 
Voici un exemple de procédure à suivre pour résoudre ce problème. Imaginons que vous suiviez une trace réseau lors d’un appel et les 20 premières minutes qu’il n’y a pas de paquets perdus, mais que vous avez un espace de 1,5 secondes de paquets et que vous avez l’habitude de le reste de l’appel. La moyenne est <de 10% (0,1) de perte de paquets même dans une analyse RTP de suivi Wireshark. Quelle a été la perte de paquets maximale ? 1,5 secondes sur une période de 5 secondes seraient de 30% (0,3). A-t-il observé au cours de la période de cinq secondes (peut-être, ou peut-être fractionné au cours de la période d’échantillonnage) ?
 
Si les métriques du réseau s’importent correctement dans les valeurs moyenne et maximale, accédez à d’autres données de télémétrie : 
- Vérifiez le ratio d’événement d’UC insuffisant pour vérifier si les ressources de l’UC détectées disponibles étaient insuffisantes et ont une mauvaise qualité. 
- Le périphérique audio est-il en mode half duplex pour éviter les commentaires en raison de micros à proximité des haut-parleurs ? 
- Vérifiez le coefficient d’événement AEC en mode half duplex. Le périphérique est-il en faute d’introduction ou de problème de micro, en raison d’une chute USB ou d’une station d’accueil USB, s’il est connecté à un concentrateur ou une station d’ancrage :  
- Vérifiez les ratios d’événement liés aux problèmes liés aux périphériques et aux problèmes de micro. Est-ce que l’appareil proprement dit fonctionne correctement ?  
- Vérifiez que l’appareil de capture et de rendu ne fonctionne pas.


Pour en savoir plus sur les dimensions et les mesures disponibles dans la télémétrie bord, voir [dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md).

Pour bruit de fond, activez la case à cocher Désactiver le coefficient d’événement pour voir la durée pendant laquelle les participants ont été désactivés.
 
Créez des rapports détaillés dans bord et filtrez sur ID de réunion pour consulter tous les utilisateurs et les flux d’une réunion et ajouter les champs qui vous intéressent. Il est possible qu’un utilisateur signalant ce problème ne soit pas celui qui rencontre le problème. Ils signalent simplement l’utilisateur.
 
La télémétrie ne sera pas nécessairement à l’origine du problème, mais elle peut vous aider à mieux comprendre la façon dont vous pouvez trouver et informer vos décisions. S’agit-il des mises à jour du réseau, du périphérique, du pilote ou du microprogramme, de l’utilisation ou de l’utilisateur ?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Pourquoi est-ce que je reçois une différence de 0,2% sur les mesures et le nombre d’utilisateurs et la façon d’obtenir des volumes plus précis ? 
Pour calculer le nombre d’appels et les mesures de nombre d’utilisateurs, une opération NB.si distincte est effectuée par rapport aux identificateurs d’appel ou d’utilisateur du jeu de données. Dans le cas d’un grand nombre de jeux de données, une erreur de 0,2% est inhérente à l’opération NB.si distincte. Pour obtenir le volume le plus précis, vous devez vous fier aux mesures de nombre de flux, car elles ne dépendent pas de cette opération NB.si distincte. Le filtrage permettant de réduire le volume de données risque de réduire l’erreur, mais n’a pas pu éliminer cette source d’erreur dans les compteurs d’appels et d’utilisateurs distincts. Reportez-vous aux [sections Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md) pour lesquels des mesures sont affectées.

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a>Pourquoi les données du rapport bord v2 sont-elles différentes de celles du rapport bord v3 ? 

Si vous voyez des différences de données entre bord v2 et v3, assurez-vous que la comparaison ou la validation des données est réalisée sur une « pommes-to-pommes » et un niveau étroit, et non sur un niveau agrégé. Par exemple, si vous filtrez les deux rapports pour les données du client de bureau MSIT de la construction de 30 ', le pourcentage de qualité médiocre doit être identique entre la version v2 et la version v3.

La classification de CQDv2 pour l’échec de la CallSetup n’est envisagée qu’à des fins de « son », dans CQDv3 cette classification se produit pour chaque modalité (audio, vidéo et partage) et est représentée dans le flux de modalité correspondant. 

Pour Teams, le CQDv2 applique les mêmes commentaires aux utilisateurs à toutes les modalités CQDv3 applique une base de commentaires à des fins d’équipe.

BORD v3 comprend 
1. Appels 2019 de Skype entreprise Server 
2. Les appels Skype bot tels que le standard automatique, la file d’attente d’appels, le service d’annonce de conférence 
3. Interface de bureau virtuel,
4. Conférences vidéo,
3. Événements en direct pour l’éditeur et les appels du présentateur 
4. Appels RTC. 

Pour plus d’informations sur l’utilisation de ces modèles Power BI pour analyser et enregistrer vos données bord, voir [utiliser les rapports Power bi pour bord](cqd-power-bi-query-templates.md).


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Pourquoi les données bord de Skype entreprise sont-elles différentes de celles bord de teams ? 


> [!IMPORTANT]
> À compter du 1er juillet 2020, l’ancien bord accède aux données à partir de la dernière bord. Les données bord plus anciennes ne sont plus disponibles et vous ne pouvez pas exporter les données de votre bâtiment ou de votre rapport.


Si vous essayez de comparer des données entre l’ancien bord du portail hérité Skype entreprise (cqd.lync.com) et le dernier bord à partir du centre d’administration Teams (cqd.teams.microsoft.com), vous remarquerez rapidement que les données ne correspondent pas. Ce n’est pas parce que les derniers rapports bord sur de nombreux scénarios d’appels supplémentaires. Si vous utilisez toujours des rapports de l’ancien bord, utilisez cet article pour vous aider à interpréter ces rapports : [tableau de bord de qualité des appels pour Skype entreprise Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).



Vous trouverez ci-dessous un exemple d’application de filtres spécifiques pour comparer les données bord v2 et bord v3 :

1. Enregistrement QoE disponible = vrai

2. Ajoutez est le filtre de paires de serveurs avec value : client : client et client : Server. La plupart des clients préfèrent exclure serveur : appels serveur.

3. Ajoutez un filtre pour la catégorie de l’agent utilisateur et filtrez le standard automatique, la file d’attente d’appels, le bot, le système de salle, le MediationServer, le service d’annonce des conférences, l’infrastructure VDI, etc.

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard1.png" alt-text="Capture d’écran de l’application de filtres spécifiques dans bord v3":::

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard2.png" alt-text="Capture d’écran de l’application de filtres spécifiques dans bord v2":::

#### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a>Autres différences attendues entre bord v2 et bord v3

Pour en savoir plus sur les différences entre les versions les plus anciennes et les plus récentes de bord, lisez le blog [Présentation du tableau de bord de qualité des appels avancé](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Introducing-the-Advanced-Call-Quality-Dashboard/ba-p/972586) , du 5 novembre 2019.


> [!IMPORTANT]
> À compter du 1er juillet 2020, l’ancien bord accède aux données à partir de la dernière bord. Les données bord plus anciennes ne sont plus disponibles et vous ne pouvez pas exporter les données de votre bâtiment ou de votre rapport.

Vous verrez probablement plus de différences de données entre vos anciens rapports bord et les plus récents au niveau agrégé ou synthétique. Si vous comparez les données à un niveau plus précis, vous obtiendrez une comparaison « pommes à pommes ». Par exemple, si vous examinez les données d’un immeuble individuel, le pourcentage de qualité médiocre doit être le même entre les anciens et les nouveaux rapports bord.

- Choisissez un scénario avec le focus étroit, tel que les connexions câblées d’entreprise, les ordinateurs de bureau Windows, ou une région ou un bâtiment unique.
- Vérifiez les plages d’adresses IP de RM, TR ou MP. Les plages d’équipes sont plus récentes que Skype entreprise Online et peuvent entraîner des problèmes de connectivité liés à des pare-feu.
- Ne pas comparer les numéros de synthèse ou de niveau supérieur. Ces comparaisons vous aideront à comparer le volume des appels de Skype entreprise Online sur une connexion câblée d’entreprise à un petit volume d’appels d’équipe sur un réseau LTE ou privé.
- Soyez attentif aux différences de décalage d’emplacement et de population : de nombreuses comparaisons sont trop différentes pour être utiles :
  - NOAM : APAC
  - NY : autorités australiennes
  - Filaire : wifi
  - Réseau d’entreprise : réseau domestique
  
### <a name="why-cant-i-see-euii-in-cqd"></a>Pourquoi ne puis-je pas voir EUII dans bord ?

Ces rôles d’administrateur peuvent accéder à bord, mais ils ne peuvent pas afficher EUII (informations d’identification de l’utilisateur final) :
- Lecteur de rapports Microsoft 365
- Spécialiste du support des communications teams

Pour en savoir plus sur les rôles qui peuvent accéder à bord, y compris les [rôles d’attribution de EUII-lecture des rôles pour accéder à bord](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Pourquoi des informations Skype entreprise s’afficheront dans bord lorsque j’ai filtré uniquement pour les équipes ?

Lorsque vous filtrez les équipes uniquement dans les rapports bord (isTeams = 1), vous filtrez tous les appels dans lesquels le *premier point de terminaison* est Teams. Si le *deuxième point de terminaison* est Skype entreprise, ces informations apparaissent dans votre rapport bord.

CQDv2 et CQDv3 ont toujours un nombre total différent, car CQDv3 aura de nouveaux scénarios qu’CQDv2 n’aura pas. C’est pourquoi comparer le total de synthèse ou les nombres cumulés cumulés sans aucun filtre n’aura de différences attendues.  

En fonction du scénario des clients, CQDv3 inclut des appels locaux marketing 2019 (si marketing 2019 est utilisé avec un connecteur de données), des appels Skype bot (AA, CVI, VDI), des événements en direct et des appels PSTN. Scénarios et fonctionnalités disponibles pour les clients, mais leurs données ne sont pas dans bord v2.

Par exemple, il est probable que vos clients et vous verrez des flux audio 200 000, avec 5000 échecs dans le rapport de synthèse bord v2. différences entre les flux audio 300 000 et les échecs 5500 (provenant de 2019 appels locaux, d’appels CVI, d’appels RTC, etc.) dans bord v3.

Pour déterminer s’il existe des différences inattendues, vous devez examiner les différentes répartitions des données globales.  Comparer avec intention.  Le fait de découper les données par paire de catégorie de l’agent utilisateur est l’un des premiers points recommandés.  Le *premier produit* et le *second produit* sont également des segments appropriés.  


## <a name="related-topics"></a>Voir aussi

[Améliorer et surveiller la qualité des appels pour teams](monitor-call-quality-qos.md)

[Qu’est-ce que bord ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels (bord)](turning-on-and-using-call-quality-dashboard.md)

[Télécharger le client et générer des données](CQD-upload-tenant-building-data.md)

[Rapports et données bord](CQD-data-and-reports.md)

[Utiliser bord pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans bord](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans bord](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser des données de bord](CQD-Power-BI-query-templates.md)

[Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)