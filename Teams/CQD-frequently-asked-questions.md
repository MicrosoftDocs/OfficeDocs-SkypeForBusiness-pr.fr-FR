---
title: Forum aux questions (FAQ) sur le tableau de bord de qualité des appels
ms.author: serdars
author: SerdarSoysal
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Lisez les questions fréquemment posées (FAQ) et les réponses sur Microsoft Teams tableau de bord de qualité des appels.
ms.openlocfilehash: 4d0d0bbbc35ac130755e61075408e9de80f1c09c
ms.sourcegitcommit: d976e49943aedd511bd6a80b02afeac4a6453406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2021
ms.locfileid: "61362541"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Forum aux questions (FAQ) sur le tableau de bord de qualité des appels

## <a name="frequently-asked-questions"></a>Questions fréquentes (FAQ)

[Pourquoi le CQD marque-t-il un appel comme « Bon » si un ou plusieurs participants à la réunion ont connu une expérience médiocre ?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Pourquoi la différence entre les valeurs des appels et du nombre d’utilisateurs sur les mesures est-elle de 0,2 % et comment obtenir les volumes les plus précis ? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Pourquoi est-ce que EUII n’est pas dans le CQD ?](#why-cant-i-see-euii-in-cqd)

[Pourquoi les informations du Skype Entreprise sont-elles disponibles dans le CQD alors que j’ai filtré les Teams uniquement ?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Pourquoi mes rapports personnalisés ne retournent-ils qu’un maximum de 10 000 lignes alors que je sais qu’il devrait y avoir davantage d’entrées ?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[Pourquoi les Wi-Fi connexions VPN s’affichent-elle sous la connexion câblé au lieu du Wi-Fi ?](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[J’ai désactivé l’enregistrement basé sur une Teams et à présent les appels d’égal à égal sont marqués en tant que conférences. Que s’est-il passé ?](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Pourquoi le CQD marque-t-il un appel comme « Bon » si un ou plusieurs participants à la réunion ont connu une expérience médiocre ?

Consultez les règles que le CQD utilise pour la [classification des flux.](stream-classification-in-call-quality-dashboard.md)
 
Pour les flux audio, les cinq classificateurs, qui sont calculés pour la moyenne en fonction de la durée de l’appel, peuvent tous être dans des paramètres de « bon ». Cela ne signifie pas que les utilisateurs n’ont pas connu de problème audio, statique ou statique. 

Pour déterminer s’il s’agit d’un problème de réseau, regardez le delta entre les valeurs moyennes de la session et les valeurs maximales. Les valeurs maximales sont les valeurs maximales détectées et signalées pendant la session.
 
Voici un exemple de la façon de résoudre ce problème. Supposons que vous prenez une trace réseau pendant un appel et que les 20 premières minutes ne perdent pas de paquets, mais qu’il y a un intervalle de 1,5 secondes de paquets, puis êtes bon pour le reste de l’appel. La moyenne sera d'<10 % (0,1) perte de paquets, même dans une analyse Wireshark trace RTP. Qu’est-ce que la perte de paquets maximale ? 1,5 secondes dans une période de 5 secondes serait 30 % (0,3). Cela s’est-il produit au cours de la période d’échantillonnage de 5 secondes (peut-être ou a-t-il pu être fractionner au cours de la période d’échantillonnage) ?
 
Si les mesures réseau semblent bonnes dans les moyennes et les valeurs max, regardez d’autres données de télémétrie : 
- Vérifiez le rapport entre les événements de l’UC insuffisant pour voir si les ressources de l’UC disponibles étaient insuffisantes et causaient une mauvaise qualité. 
- Le périphérique audio était-il en mode semi-recto verso pour empêcher les commentaires en raison de microphones qui se rapprochent des haut-parleurs ? 
- Vérifiez le ratio événement AEC semi-recto verso de l’appareil. L’appareil a-t-il été en panne ou le micro a-t-il introduit un bruit ou un problème statique suite à des sorties audio USB branchées à un hub ou à une station d’accueil ?  
- Vérifiez les proportions des événements des problèmes de périphérique et de micro. L’appareil fonctionnait-il correctement ?  
- Vérifiez les proportions des événements du périphérique de capture et de rendu, qui ne fonctionnent pas.


Pour plus d’informations sur les dimensions et les mesures disponibles dans la télémétrie du tableau de bord de qualité des appels, consultez les dimensions et les mesures disponibles dans le [tableau de bord de qualité des appels.](dimensions-and-measures-available-in-call-quality-dashboard.md)

Pour les bruits de fond, vérifiez le son des événements pour voir le temps pendant que les participants ont été muets.
 
Créez des rapports détaillés dans le DQD et filtrez sur l’ID de réunion pour examiner tous les utilisateurs et flux d’une réunion et ajouter les champs qui vous intéressent. Il est possible qu’un utilisateur signalant le problème ne soit pas celui qui en était à l’état. Ils ne font que signaler l’expérience.
 
La télémétrie n’appelle pas nécessairement le problème, mais vous permet de mieux comprendre où chercher et informer vos décisions. S’agit-il de mises à jour de réseau, d’appareil, de pilote ou de microprogramme, d’utilisation ou d’utilisateur ?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Pourquoi la différence entre les valeurs des appels et du nombre d’utilisateurs sur les mesures est-elle de 0,2 % et comment obtenir les volumes les plus précis ? 

Pour calculer le nombre d’appels et les mesures du nombre d’utilisateurs, une opération de comptage distincte est effectuée par rapport à l’appel ou aux identificateurs d’utilisateur dans la série de données. Sur les jeux de données de grande taille, il existe une erreur de 0,2 % intrinsèque à l’opération de comptage distincte. Pour obtenir le volume le plus précis, vous devez compter sur des mesures de décompte de flux, car elles ne s’appuient pas sur cette opération de comptage distincte. Le filtrage pour réduire le volume des données peut réduire l’erreur, mais n’élimine pas cette source d’erreur dans des appels et des nombres d’utilisateurs distincts. [Reportez-vous aux dimensions et mesures disponibles dans le tableau](dimensions-and-measures-available-in-call-quality-dashboard.md) de bord de qualité des appels pour lesquelles les mesures sont impactées.

  
### <a name="why-cant-i-see-euii-in-cqd"></a>Pourquoi est-ce que EUII n’est pas dans le CQD ?

Ces rôles d’administrateur peuvent accéder au DQD, mais ils ne peuvent pas afficher la fonction EUII (informations d’identification utilisateur final) :

- Microsoft 365 de rapports
- Teams du support technique pour les communications

Pour en savoir plus sur les rôles qui peuvent accéder au CQD, y compris EUII, lisez Attribuer des rôles pour accéder au [CQD.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Pourquoi les informations du Skype Entreprise sont-elles disponibles dans le CQD alors que j’ai filtré les Teams uniquement ?

Lorsque vous filtrez des Teams uniquement dans les rapports du CQD (isTeams =  1), vous filtrez pour tous les appels pour lequel le premier point de terminaison est Teams. Si le *deuxième point de terminaison* Skype Entreprise point de terminaison, ces informations s’afficheront dans votre rapport du CQD.

Le nombre total des valeurs des groupes CQDv2 et CQDv3 sera toujours différent, car celui-ci aura de nouveaux scénarios que le VQDv2 n’aura pas. C’est pourquoi la comparaison de total de synthèse ou de nombres complets agrégés sans filtres aura ces différences attendues.  

Selon le scénario de clients, le CQDv3 inclut les appels locaux SFB 2019 (si SFB 2019 est utilisé avec un connecteur de données), les appels Skype Bot (AA, CVI, VDI), les événements en direct et les appels RXT. Scénarios/fonctionnalités disponibles pour les clients, mais leurs données ne sont pas accessibles dans le CQD V2.

Par exemple, vos clients et vous verrez par exemple 200 000 flux audio, avec 5 000 échecs dans le rapport de synthèse CQD V2, et 300 000 flux audio avec 5 5000 échecs (provenant d’appels locaux 2019, appels CVI, appels RSTN, etc.) dans le tableau de bord de qualité des appels V3.

Pour déterminer s’il existe des différences inattendues, vous devez examiner différentes répartitions des données globales.  Comparer avec l’objectif.  La catégorie de l’agent utilisateur est l’une des premières recommandations.  *First Product* et *Second Product* sont également de bons slicers.  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Pourquoi mes rapports personnalisés ne retournent-ils qu’un maximum de 10 000 lignes alors que je sais qu’il devrait y avoir davantage d’entrées ?

Le CQD est conçu pour les requêtes de données résumées et n’est pas conçu pour l’exportation des données. Nous vous recommandons de rendre vos rapports plus rapidement possible afin d’éviter le dépassement de la limite de 10 000 lignes. Commencez par regarder vos KPIs en utilisant des dimensions de cardinalité plus larges et inférieures, telles que Mois, Année, Date, Région, Pays, etc. À partir de là, vous pouvez descendre dans les dimensions de plus en plus grande cardinalité. Les rapports d’aide et de Location-Enhanced fournissent de bons exemples de ce flux de travail d’drill down.

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>Pourquoi les Wi-Fi connexions VPN s’affichent-elle sous la connexion câblé au lieu du Wi-Fi ?

Il s'agit d'un comportement normal. Le fournisseur VPN a créé un adaptateur ethernet virtuel qui est traité comme une connexion câblé. Dans la mesure où il n’est pas correctement étiqueté, le système d’exploitation ne sait pas qu’il s’agit d’une connexion Wi-Fi et l’indique comme étant câblé.

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>J’ai désactivé l’enregistrement basé sur une Teams et à présent les appels d’égal à égal sont marqués en tant que conférences. Que s’est-il passé ?

Ce comportement est prévu lorsque l’enregistrement basé sur une stratégie est activé dans Microsoft Teams. L’enregistrement basé sur une stratégie utilise un robot Teams enregistreur déployé dans Microsoft Azure pour capturer le contenu des réunions à des fins de conformité. Étant donné qu’un robot enregistreur est lui-même une partie de l’appel, il ne s’agit plus d’un appel d’égal à égal, mais d’un appel à plusieurs. Les appels à plusieurs sont classés comme conférences par Microsoft Teams et sont donc indiqués comme tels lorsque vous affichez ces appels dans le CQD et d’autres outils de qualité des appels.

## <a name="related-articles"></a>Articles connexes

[Améliorer et surveiller la qualité des appels pour les Teams](monitor-call-quality-qos.md)

[Qu’est-ce que le CQD ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels](turning-on-and-using-call-quality-dashboard.md)

[Télécharger données client et bâtiment](CQD-upload-tenant-building-data.md)

[Données et rapports du CQD](CQD-data-and-reports.md)

[Utiliser le CQD pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans le DQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans le DQD](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données du CQD](CQD-Power-BI-query-templates.md)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
