---
title: Questions fréquentes (FAQ) sur le tableau de bord de qualité des appels (CQD)
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
description: Lisez les questions fréquentes (FAQ) et les réponses sur Microsoft Teams tableau de bord de qualité des appels (CQD).
ms.openlocfilehash: f320bab549ee322c1254babd0feb49cc24419215
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823203"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Questions fréquentes (FAQ) sur le tableau de bord de qualité des appels (CQD)

## <a name="frequently-asked-questions"></a>Questions fréquentes (FAQ)

[Pourquoi le CQD marque-t-il un appel comme « Bon » si un ou plusieurs participants à la réunion ont eu une mauvaise expérience ?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Pourquoi y a-t-il jusqu’à 0,2 % de différence entre les valeurs d’appel et de nombre d’utilisateurs sur les mesures et comment obtenir des volumes plus précis ? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Pourquoi ne puis-je pas voir EUII dans CQD ?](#why-cant-i-see-euii-in-cqd)

[J’essaie d’utiliser CQD pour les rapports de type d’utilisation et de constater que certaines données sont incomplètes. Pourquoi cela ?](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[Pourquoi vois-je Skype Entreprise informations dans CQD quand j’ai filtré pour Teams uniquement ?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Pourquoi mes rapports personnalisés retournent-ils seulement un maximum de 10 000 lignes quand je sais qu’il devrait y avoir plus d’entrées ?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[Pourquoi Wi-Fi connexions VPN s’affichent-elles comme étant câblées au lieu du Wi-Fi ?](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[J’ai activé l’enregistrement basé sur les stratégies dans Teams et maintenant les appels P2P sont marqués comme des conférences. Que s’est-il passé ?](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Pourquoi le CQD marque-t-il un appel comme « Bon » si un ou plusieurs participants à la réunion ont eu une mauvaise expérience ?

Découvrez les règles utilisées par CQD pour la [classification de flux](stream-classification-in-call-quality-dashboard.md).
 
Pour les flux audio, l’un des cinq classifieurs (calculés pour la moyenne en fonction de la longueur de l’appel) peut tous se trouver dans des paramètres « corrects ». Cela ne signifie pas que les utilisateurs n’ont pas rencontré quelque chose qui a contribué à une suppression audio, statique ou un problème. 

Pour déterminer s’il s’agissait d’un problème réseau, examinez le delta entre les valeurs moyennes de la session et les valeurs maximales. Les valeurs maximales sont le maximum détecté et signalé pendant la session.
 
Voici un exemple de résolution de cette situation. Supposons que vous preniez une trace réseau pendant un appel et que les 20 premières minutes il n’y a pas de paquets perdus, mais que vous avez un intervalle de 1,5 seconde de paquets, puis bon pour le reste de l’appel. La moyenne va être <10 % (0,1) Perte de paquets, même dans une analyse RTP de trace Wireshark. Quelle a été la perte maximale de paquets ? 1,5 seconde au cours d’une période de 5 secondes serait de 30 % (0,3). Est-ce que cela s’est produit au cours de la période d’échantillonnage de 5 secondes (peut-être ou qu’il pourrait être fractionné au cours de la période d’échantillonnage) ?
 
Si les métriques réseau sont correctes dans les moyennes et les valeurs maximales, recherchez d’autres données de télémétrie : 
- Vérifiez le taux d’événements insuffisants de l’UC pour voir si les ressources d’UC détectées disponibles étaient insuffisantes et provoquaient une mauvaise qualité. 
- L’appareil audio était-il en mode Semi-Duplex pour empêcher les commentaires en raison de microphones trop proches des haut-parleurs ? 
- Vérifiez le ratio d’événements AEC duplex demi-appareil. Un problème est-il dû à un appareil, tel qu’un microphone, à l’introduction de bruit ou statique en raison de sorties audio USB lorsqu’il est branché à un hub ou à une station d’accueil ?  
- Vérifiez les taux d’événements des problèmes d’appareil et du microphone. L’appareil lui-même fonctionnait-il correctement ?  
- Vérifiez les taux d’événements de capture et de rendu de l’appareil qui ne fonctionne pas.


Pour plus d’informations sur les dimensions et les mesures disponibles dans les données de télémétrie CQD, lisez [Dimensions et mesures disponibles dans le tableau de bord qualité des](dimensions-and-measures-available-in-call-quality-dashboard.md) appels.

Pour le bruit de fond, vérifiez le rapport d’événements de désactivation pour voir la durée pendant laquelle les participants ont été désactivés.
 
Créez des rapports détaillés dans CQD et filtrez l’ID de réunion pour examiner tous les utilisateurs et flux d’une réunion et ajouter les champs qui vous intéressent. Un utilisateur signalant le problème n’est peut-être pas celui qui a rencontré le problème. Ils signalent simplement l’expérience.
 
La télémétrie n’appellera pas nécessairement le problème, mais elle peut vous aider à mieux comprendre où rechercher et informer vos décisions. S’agit-il des mises à jour du réseau, de l’appareil, du pilote ou du microprogramme, de l’utilisation ou de l’utilisateur ?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Pourquoi y a-t-il jusqu’à 0,2 % de différence entre les valeurs d’appel et de nombre d’utilisateurs sur les mesures et comment obtenir des volumes plus précis ? 

Pour calculer le nombre d’appels et les mesures de nombre d’utilisateurs, une opération countif distincte est effectuée par rapport aux identificateurs d’appel ou d’utilisateur dans le jeu de données. Sur les jeux de données volumineux, une erreur pouvant atteindre 0,2 % est inhérente à l’opération countif distincte. Pour le volume le plus précis, vous devez vous appuyer sur les mesures de nombre de flux, car elles ne reposent pas sur cette opération countif distincte. Le filtrage pour réduire le volume de données peut réduire l’erreur, mais ne peut pas éliminer cette source d’erreur dans les nombres d’appels et d’utilisateurs distincts. Reportez-vous aux [dimensions et mesures disponibles dans le tableau de bord qualité](dimensions-and-measures-available-in-call-quality-dashboard.md) des appels pour lesquels les mesures sont affectées.

  
### <a name="why-cant-i-see-euii-in-cqd"></a>Pourquoi ne puis-je pas voir EUII dans CQD ?

Ces rôles d’administrateur peuvent accéder au CQD, mais ils ne peuvent pas afficher EUII (informations d’identification de l’utilisateur final) :

- Lecteur de rapports Microsoft 365
- Spécialiste du support des communications Teams

Pour en savoir plus sur les rôles qui peuvent accéder au CQD , y compris EUII, lisez [Attribuer des rôles pour accéder au CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>J’essaie d’utiliser CQD pour les rapports de type d’utilisation et de constater que certaines données sont incomplètes. Pourquoi cela ?

Les outils de gestion de la qualité des appels tels que CQD, Call Analytics, CallRecord API Graph et Real-time Analytics sont basés sur la télémétrie de diagnostic. Les informations que nous affichons dans Teams outils de gestion de la qualité des appels sont aussi complètes que les données de télémétrie que nous recevons des clients participant à un appel. Il existe plusieurs raisons pour lesquelles nous ne pouvons pas recevoir de données de télémétrie complètes, telles que des pannes de réseau ou des [configurations incorrectes de pare-feu ou de proxy](/microsoft-365/enterprise/urls-and-ip-address-ranges). Nous continuons à travailler pour améliorer la fiabilité et la résilience avec lesquelles Teams clients fournissent des données de télémétrie au service.

Dans cet esprit, nous ne prenons pas en charge l’utilisation d’outils de gestion de la qualité des appels pour la création de rapports d’utilisation. Elles ne sont pas conçues pour prendre en charge ni pour ces types de scénarios de création de rapports, et de nombreuses statistiques d’utilisation ne sont pas et ne seront pas disponibles dans ces outils. Teams Administration Center propose une série de [rapports d’utilisation](teams-analytics-and-reports/teams-reporting-reference.md), et un [rapport de participation aux réunions](teams-analytics-and-reports/meeting-attendance-report.md) est disponible directement à partir du client Teams.

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Pourquoi vois-je Skype Entreprise informations dans CQD quand j’ai filtré pour Teams uniquement ?

Lorsque vous filtrez pour Teams uniquement dans les rapports CQD (isTeams = 1), vous filtrez pour tous les appels où le *premier point de terminaison* est Teams. Si le *deuxième point de terminaison* est Skype Entreprise, ces informations s’affichent dans votre rapport CQD. Selon les scénarios des clients, le CQD peut inclure des appels Skype Entreprise Server 2019 lors de la configuration du [connecteur de données d’appel](/skypeforbusiness/hybrid/plan-call-data-connector). Il peut également inclure des appels de bot Skype (AA, CVI, VDI), des événements en direct et des appels RTC.

Il est possible de supprimer Skype Entreprise informations de vos requêtes en filtrant sur des dimensions telles que *la catégorie Premier agent utilisateur* et *Deuxième catégorie d’agent utilisateur*. Vous pouvez également utiliser la *paire de catégories de l’agent utilisateur* qui combine les dimensions First et Second dans un seul filtre.

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Pourquoi mes rapports personnalisés retournent-ils seulement un maximum de 10 000 lignes quand je sais qu’il devrait y avoir plus d’entrées ?

CQD est conçu pour les requêtes de données résumées et n’est pas conçu pour l’exportation des données. Nous vous recommandons de restructurer vos rapports, si possible, pour empêcher le dépassement de la limite de 10 000 lignes. Commencez par examiner vos indicateurs de performance clés à l’aide de dimensions de cardinalité plus larges et inférieures, telles que Mois, Année, Date, Région, Pays, etc. À partir de là, vous pouvez explorer des dimensions de cardinalité de plus en plus élevées. Les rapports helpdesk et Location-Enhanced fournissent tous deux de bons exemples de ce flux de travail d’exploration.

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>Pourquoi Wi-Fi connexions VPN s’affichent-elles comme étant câblées au lieu du Wi-Fi ?

Il s'agit d'un comportement normal. Le fournisseur VPN a créé une carte ethernet virtuelle qui est traitée comme une connexion câblée. Étant donné qu’il n’est pas correctement étiqueté, le système d’exploitation ne sait pas qu’il s’agit d’une connexion Wi-Fi et le signale comme câblé.

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>J’ai activé l’enregistrement basé sur les stratégies dans Teams et maintenant les appels P2P sont marqués comme des conférences. Que s’est-il passé ?

Ce comportement est attendu lorsque l’enregistrement basé sur des stratégies est activé dans Microsoft Teams. L’enregistrement basé sur des stratégies utilise un bot d’enregistreur Teams déployé dans Microsoft Azure pour capturer le contenu de la réunion à des fins de conformité. Dans la gestion de la qualité des appels, « pair à pair » est une description du flux du trafic multimédia, et non de l’interaction entre les utilisateurs. Étant donné qu’un bot enregistreur est lui-même partie à l’appel, l’appel n’est plus pair à pair, mais un appel multiparte. Les appels multipartis sont classés en tant que conférences par Microsoft Teams. Ils sont donc indiqués en tant que tels lorsque vous affichez ces appels dans CQD et d’autres outils de qualité des appels.

## <a name="related-articles"></a>Articles connexes

[Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md)

[Qu’est-ce que le TBQA ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Charger le client et créer des données](CQD-upload-tenant-building-data.md)

[Données et rapports du TBQA](CQD-data-and-reports.md)

[Utiliser le TBQA pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans le TBQA](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le TBQA](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données TBQA](CQD-Power-BI-query-templates.md)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
