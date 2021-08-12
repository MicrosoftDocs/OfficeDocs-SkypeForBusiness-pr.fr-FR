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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Lisez les questions fréquemment posées (FAQ) et les réponses sur Microsoft Teams tableau de bord de qualité des appels.
ms.openlocfilehash: b6d2782418b2cba1c7268fdadad7c577a4730c18ddfb84903d13535185c2dd7b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334845"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Forum aux questions (FAQ) sur le tableau de bord de qualité des appels

## <a name="frequently-asked-questions"></a>Foire aux questions

[Pourquoi le CQD marque-t-il un appel comme « Bon » si un ou plusieurs participants à la réunion ont connu une expérience médiocre ?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Pourquoi est-ce que je vois jusqu’à 0,2 % de différences entre les valeurs des appels et du nombre d’utilisateurs sur les mesures et comment obtenir les volumes les plus précis ? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[En quoi les données du Skype Entreprise sont-elles différentes des données du même Teams ?](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[Pourquoi est-ce que EUII n’est pas dans le CQD ?](#why-cant-i-see-euii-in-cqd)

[Pourquoi est-ce que je Skype Entreprise des informations dans le CQD alors que j’ai filtré Teams uniquement ?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Pourquoi mes rapports personnalisés ne retournent-ils qu’un maximum de 10 000 lignes alors que je sais qu’il devrait y avoir davantage d’entrées ?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[Pourquoi les connexions VPN WiFi s’affichent-elle sous la connexion filée au lieu du WiFi ?](#why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Pourquoi le CQD marque-t-il un appel comme « Bon » si un ou plusieurs participants à la réunion ont connu une expérience médiocre ?

Consultez les règles que le CQD utilise pour la [classification des flux.](stream-classification-in-call-quality-dashboard.md)
 
Pour les flux audio, les cinq classificateurs, calculés pour la moyenne en fonction de la durée de l’appel, peuvent tous être dans des paramètres de « bon ». Cela ne signifie pas que les utilisateurs n’ont pas participé à un problème audio, statique ou statique. 

Pour déterminer s’il s’agit d’un problème réseau, regardez le delta entre les valeurs moyennes de la session et les valeurs maximales. Les valeurs maximales sont les valeurs maximales détectées et signalées pendant la session.
 
Voici un exemple de la façon de résoudre ce problème. Supposons que vous prenez une trace réseau pendant un appel et que les 20 premières minutes ne perdent pas de paquets, mais qu’il y a un intervalle de 1,5 secondes de paquets, puis que vous êtes bon pour le reste de l’appel. La moyenne sera d'<10 % (0,1) perte de paquets, même dans une analyse RTP de trace Wireshark. Qu’est-ce que la perte de paquets maximale ? 1,5 secondes dans une période de 5 secondes serait 30 % (0,3). Cela s’est-il produit au cours de la période d’échantillonnage de 5 secondes (peut-être ou a-t-il pu être fractioné pendant la période d’échantillonnage) ?
 
Si les mesures réseau semblent bonnes dans les moyennes et les valeurs max, regardez d’autres données de télémétrie : 
- Vérifiez le rapport entre les événements de l’UC insuffisant pour voir si les ressources de l’UC disponibles étaient insuffisantes et causaient une mauvaise qualité. 
- Le périphérique audio était-il en mode semi-recto verso pour empêcher les commentaires en raison de microphones qui se rapprochent des haut-parleurs ? 
- Vérifiez le ratio événement AEC semi-recto verso de l’appareil. L’appareil a-t-il été en panne ou le micro a-t-il introduit un bruit ou un problème statique suite à des sorties audio USB branchées à un hub ou à une station d’accueil ?  
- Vérifiez les proportions des événements des problèmes de périphérique et de micro. L’appareil fonctionnait-il correctement ?  
- Vérifiez les proportions des événements du périphérique de capture et de rendu, qui ne fonctionnent pas.


Pour plus d’informations sur les dimensions et les mesures disponibles dans la télémétrie du tableau de bord de qualité des appels, consultez les dimensions et les mesures disponibles dans le [tableau de bord de qualité des appels.](dimensions-and-measures-available-in-call-quality-dashboard.md)

Pour les bruits de fond, vérifiez le son des événements pour voir le temps pendant que les participants ont été muets.
 
Créez des rapports détaillés dans le DQD et filtrez sur l’ID de réunion pour examiner tous les utilisateurs et les flux d’une réunion et ajouter les champs qui vous intéressent. Il est possible qu’un utilisateur signalant le problème ne soit pas celui qui en était à l’état. Ils ne font que signaler l’expérience.
 
La télémétrie n’appelle pas nécessairement le problème, mais vous permet de mieux comprendre où chercher et informer vos décisions. S’agit-il de mises à jour réseau, appareil, pilote ou microprogramme, utilisation ou utilisateur ?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Pourquoi est-ce que je vois jusqu’à 0,2 % de différences entre les valeurs des appels et du nombre d’utilisateurs sur les mesures et comment obtenir les volumes les plus précis ? 
Pour calculer le nombre d’appels et les mesures du nombre d’utilisateurs, une opération de comptage distincte est effectuée par rapport à l’appel ou aux identificateurs d’utilisateur dans la série de données. Sur les jeux de données de grande taille, il existe une erreur de 0,2 % intrinsèque à l’opération de comptage distincte. Pour obtenir le volume le plus précis, vous devez vous fier aux mesures de comptage des flux, car elles ne s’appuient pas sur cette opération de comptage distincte. Le filtrage pour réduire le volume des données peut réduire l’erreur, mais n’élimine pas cette source d’erreur dans des appels et des nombres d’utilisateurs distincts. [Reportez-vous aux dimensions et mesures disponibles dans le tableau de](dimensions-and-measures-available-in-call-quality-dashboard.md) bord de qualité des appels pour lesquelles les mesures sont impactées.


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>En quoi les données du Skype Entreprise sont-elles différentes des données du même Teams ? 


> [!IMPORTANT]
> Depuis le 1er juillet 2020, l’ancien DQD (CQD.lync.com) utilise les données du dernier CQD (CQD.Teams.microsoft.com). Les anciennes données du CQD ne sont plus disponibles et vous ne pouvez pas exporter vos données de bâtiment ou de rapport. Vous pouvez toujours utiliser CQD.lync.com (disponible dans le Centre d’administration Skype Entreprise), mais nous désactiverons bientôt l’accès à CQD.lync.com. Vous devez donc accéder au CQD. Teams.microsoft.com si vous ne l’avez pas déjà fait.


Si vous essayez de comparer les données entre l’ancien CQD à partir du portail hérité d’Skype Entreprise (cqd.lync.com) et le dernier DQD du Centre d’administration Teams (cqd.teams.microsoft.com), vous remarquerez rapidement que les données ne correspondent pas. En raison des rapports les plus récents du CQD sur de nombreux scénarios d’appel supplémentaires. Si vous utilisez toujours des rapports de l’ancien tableau de bord de qualité des appels, utilisez cet article pour vous aider à interpréter ces rapports : Tableau de bord de qualité des appels [pour Skype Entreprise Server.](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)


  
### <a name="why-cant-i-see-euii-in-cqd"></a>Pourquoi est-ce que EUII n’est pas dans le CQD ?

Ces rôles d’administrateur peuvent accéder au DQD, mais ils ne peuvent pas afficher euII (informations d’identification utilisateur final) :
- Microsoft 365 Lecteur de rapports
- Teams Spécialiste du support pour les communications

Pour en savoir plus sur les rôles qui peuvent accéder au CQD, y compris EUII, lisez Attribuer des rôles pour accéder au [CQD.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Pourquoi est-ce que je Skype Entreprise des informations dans le CQD alors que j’ai filtré Teams uniquement ?

Lorsque vous filtrez des Teams uniquement dans les rapports du CQD (isTeams =  1), vous filtrez pour tous les appels pour lequel le premier point de terminaison Teams. Si le *deuxième point de terminaison* Skype Entreprise point de terminaison, ces informations s’afficheront dans votre rapport du CQD.

Les totaux des groupes CQDv2 et CQDv3 seront toujours différents, car ils auront de nouveaux scénarios que le CQDv2 n’aura pas. C’est pourquoi la comparaison de total de synthèse ou de nombres complets agrégés sans filtres aura ces différences attendues.  

Selon le scénario de clients, le CQDv3 inclut les appels locaux SFB 2019 (si SFB 2019 est utilisé avec un connecteur de données), les appels Skype Bot (AA, CVI, VDI), les événements en direct et les appels RXT. Scénarios/Fonctionnalités disponibles pour les clients, mais leurs données ne sont pas accessibles dans le CQD V2.

Par exemple, vos clients et vous verrez 200 000 flux audio, avec 5 000 échecs dans le rapport de synthèse de qualité des fichiers V2. par rapport à 300 000 flux audio avec 5 500 échecs (provenant d’appels locaux 2019, appels CVI, appels RSTN, etc.) dans le CQD V3.

Pour déterminer s’il existe des différences inattendues, vous devez examiner les différentes répartitions des données globales.  Comparer avec l’objectif.  La catégorie de l’agent utilisateur est l’une des premières recommandations.  *First Product* et *Second Product* sont également de bons slicers.  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Pourquoi mes rapports personnalisés ne retournent-ils qu’un maximum de 10 000 lignes alors que je sais qu’il devrait y avoir davantage d’entrées ?

Le CQD est conçu pour les requêtes de données résumées et n’est pas conçu pour l’exportation de données. Nous vous recommandons de rendre vos rapports plus rapidement possible afin d’éviter le dépassement de la limite de 10 000 lignes. Commencez par regarder vos KPIs à l’aide de dimensions plus larges et de cardinalité inférieure, telles que Mois, Année, Date, Région, Pays, etc. À partir de là, vous pouvez descendre dans les dimensions de plus en plus grande cardinalité. Les rapports d’aide et de Location-Enhanced fournissent de bons exemples de ce flux de travail d’drill down.

### <a name="why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi"></a>Pourquoi les connexions VPN WiFi s’affichent-elle sous la connexion filée au lieu du WiFi ?

Ceci est normal. Le fournisseur VPN a créé un adaptateur ethernet virtuel qui est traité comme une connexion câblé. Dans la mesure où il n’est pas correctement étiqueté, le système d’exploitation ne sait pas qu’il s’agit d’une connexion WiFi et l’indique comme étant câblé.

## <a name="related-topics"></a>Voir aussi

[Améliorer et surveiller la qualité des appels pour les Teams](monitor-call-quality-qos.md)

[Qu’est-ce que le CQD ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels](turning-on-and-using-call-quality-dashboard.md)

[Télécharger données de bâtiment et de client](CQD-upload-tenant-building-data.md)

[Données et rapports du CQD](CQD-data-and-reports.md)

[Utiliser le CQD pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans le DQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans le CQD](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données du CQD](CQD-Power-BI-query-templates.md)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
