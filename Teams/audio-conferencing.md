---
title: "Audioconférence dans Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Guide pratique pour le déploiement de l’audioconférence dans Microsoft Teams."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 5a65f305d924c5e5e6dac01d2391a62d8abd1243
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2017
---
<a name="audio-conferencing-in-microsoft-teams"></a>Audioconférence dans Microsoft Teams
=====================================

> [!IMPORTANT]
> L’audioconférence est en préversion publique. Elle est disponible pour les utilisateurs précoces et les utilisateurs de la préversion et est susceptible d’être modifiée lors de sa publication ou mise à jour.

L’audioconférence dans Office 365 (appelée auparavant Conférence PSTN) permet aux participants de rejoindre vos réunions depuis n’importe quel téléphone. Cette fonction est maintenant disponible dans Microsoft Teams, en préversion publique, et permet aux utilisateurs de rejoindre des réunions Teams en utilisant leurs téléphones. Le guide pratique dans cet article vous dirige étape par étape à travers le parcours du client FastTrack Office 365 pour l’audioconférence : planifier, intégrer et générer une valeur ajoutée.

Voici les avantages de [l’audioconférence](https://go.microsoft.com/fwlink/?linkid=858992) dans Office 365.

> [!NOTE]
> L’audioconférence prend en charge Teams et Skype Entreprise Online. Actuellement, le centre d’administration de Skype Entreprise et le PowerShell distant existants fournissent les interfaces d’administration permettant de gérer l’audioconférence.


|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AGPvaW4Vg0o" frameborder="0" allowfullscreen></iframe>   | |

Concevoir <a name="Envision_AudioConferencing"> </a>
=========

La phase Planifier fournit les bases du parcours du client Office 365 et s’applique à toutes les charges de travail comme l’audioconférence.

Dans cette phase, les objectifs de l’entreprise sont déterminés, avec les parties prenantes impliquées dans le projet réunies, pour fournir par la suite :

-   un plan de réussite général contenant les cas d’utilisation professionnelle, les parties prenantes clés, les objectifs et les résultats clés, les indicateurs de succès clés, les risques, l’évaluation de l’environnement, la préparation à l’adoption et un plan opérationnel.

-   Ensuite, un plan d’implémentation technique de l’audioconférence détaillé pour parvenir à l’état final souhaité.

<a name="define-business-use-cases-for-audio-conferencing"></a>Définir les cas d'utilisation professionnelle de l'audioconférence
------------------------------------------------

L’audioconférence fournit aux organisations des points d’entrée supplémentaires à toutes les réunions planifiées en permettant aux participants de rejoindre les réunions via PSTN en composant des numéros de téléphone de ligne fixe traditionnels, PBX ou de mobile.

Cela est utile lorsque la personne qui a organisé la réunion ou les participants ne se trouvent pas devant un ordinateur, ou lorsque les connexions de données sont indisponibles ou non fiables pour prendre en charge des communications vocales - par exemple lorsque les participants se trouvent dans une zone avec une couverture de données mobiles inégale, ou s’ils sont connectés à un service Wi-Fi gratuit public avec une bande passante limitée, ou lorsqu'ils préfèrent rejoindre la réunion à l’aide d'un point de terminaison de téléphonie qui leur est facilement accessible.

Dans cette étape, les principales parties prenantes impliquées dans le projet définiront des cas d’utilisation professionnelle qui prennent en charge l’implémentation de l’audioconférence.

Les cas d’utilisation professionnelle sont destinés à définir et documenter des résultats de l’entreprise attendus et mesurables, et incluent les éléments suivants :

-   Description du processus d’entreprise actuel.

-   Difficultés par rapport au processus d’entreprise existant définies.

-   Comment la technologie peut aider à surmonter ces difficultés.

-   Le résultat de l'entreprise attendu et mesurable si ces difficultés sont surmontées.

<table>
<tbody>
<tr class="header">
<th align="left"><p><img src="media/audio_conferencing_image2.png" /></p></th>
<td align="left"><p><strong>Description du processus d’entreprise actuel</strong></p>
<p>Contoso fait actuellement appel à des services de conférence PSTN fournis par le fournisseur de téléphonie local titulaire facturés par minutes de réunion pour les réunions internes et celles impliquant des parties externes.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image3.png" /></p></td>
<td align="left"><p><strong>Difficultés par rapport au processus d’entreprise existant</strong></p>
<p>Contoso dépense environ 1 million de dollars par an pour le service de conférence PSTN actuel, les réunions internes représentant 75 % du coût.</p>
<p>L’utilisation de points de terminaison de téléphonie traditionnels pour participer aux réunions hébergées par le service de conférence PSTN ne correspond pas au plan pour que l’organisation adopte Teams comme plate-forme de communication et de collaboration moderne.</p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="media/audio_conferencing_image4.png" /></p></td>
<td align="left"><p><strong>Comment la technologie peut surmonter ces difficultés</strong></p>
<p>Avec l’adoption de Microsoft Teams comme plate-forme de communication et de collaboration moderne, les utilisateurs internes devraient principalement rejoindre les réunions en utilisant leurs PC équipés de casques optimisés et de dispositifs de salle de réunion. Le service d’audioconférence sera disponible pour prendre en charge les participants externes ou les situations où l’utilisation de l’audio sur PC n’est pas avantageuse pour les participants internes.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image5.png" /></p></td>
<td align="left"><p><strong>Résultats de l’entreprise attendus et mesurables</strong></p>
<p>Le passage à Teams comme plate-forme de communication et de collaboration moderne, combinée au service d’audioconférence, réduira considérablement le coût de la prestation du service de conférence PSTN, Contoso devant dépenser seulement 20 % environ du coût annuel du service de conférence PSTN existant.</p></td>
</tr>
</tbody>
</table>

_Tableau 1 - exemple de cas d’utilisation professionnelle_


En plus de définir les cas d’utilisation professionnelle, avoir une vision claire de la portée organisationnelle et du planning du projet à cette étape permet de passer à l’étape suivante de la phase Planifier.

<a name="identify-key-stakeholders"></a>Identifier les parties prenantes clés
-------------------------

Les cas d’utilisation professionnelle définis à l’étape précédente incluront la portée organisationnelle de l’implémentation de l’audioconférence et, de ce fait, la matrice complète des parties prenantes peut être complétée pour inclure les personnes adéquates à inclure dans le projet.

<table>
<thead>
<tr class="header">
<th align="left">Rôle</th>
<th align="left">Description</th>
<th align="left">Nom, informations de contact, emplacement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Sponsor exécutif du projet</strong></td>
<td align="left"><ul><li>Autorité et responsabilité ultimes du projet et réalisation des objectifs du projet</li>
<li>Aide à résoudre les problèmes transmis par le chef de projet</li>
<li>Organise la communication au sein de l’entreprise au sujet des objectifs du projet</li>
<li>Chargé de prendre les décisions stratégiques clés</li>
<li>Chargé de la disponibilité des ressources nécessaires et du budget</p>
<li>Principale évaluation trimestrielle des activités</li>
<li>Adhésion et appui à la campagne de sensibilisation</li>
<li>Est le sponsor du projet pour le lancement du programme</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Chef de projet</strong></td>
<td align="left"><ul><li>Gestion et direction de l’équipe du projet</li>
<li>Coordonne les partenaires et les équipes qui participent au projet</li>
<li>Responsable de la création et de la gestion des plans du projet pour obtenir les principaux résultats trimestriels</li>
<li>Résoudre les problèmes fonctionnels croisés</li>
<li>Fournir des informations actualisées périodiques aux sponsors du projet</li>
<li>Incorporer les aspects relatifs à l’adoption dans l’ensemble du plan du projet</li>
<li>Diriger les évaluations mensuelles des activités et opérationnelles, contribuer aux évaluations trimestrielles des activités</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Chef/architecte de la collaboration</strong></td>
<td align="left"><ul><li>Chargé de l’exécution de la stratégie de collaboration définie par la direction de l’entreprise</li>
<li>Analyse et choisit les produits de collaboration pour l’entreprise permettant d’atteindre les objectifs professionnels</li>
<li>Chargé de la conception des opérations des produits de collaboration</li>
<li>Définit un modèle d'opération et de prise en charge</li>
<li>Contribue aux évaluations mensuelles et trimestrielles des activités</li><ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Consultant</strong></td>
<td align="left"><ul><li>Chargé des services de configuration</li>
<li>Contribue à l'architecture de solutions globale</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Gestionnaire de projets</strong></td>
<td align="left"><ul><li>Élaborer et tenir à jour les plans de projet</li>
<li>Gérer les livrables du projet conformément au plan et au budget du projet</li>
<li>Noter et gérer les problèmes liés au projet, y compris les remontées</li>
<li>Effectuer des appels d'intervention hebdomadaires</li>
<li>Assurer la liaison avec, et fournir des informations actualisées aux sponsors exécutifs du projet</li>
<li>Collaborer avec l’architecte pour définir le mode de gestion des changements et les plans de communication</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Spécialiste en gestion des changements/adoption</strong></td>
<td align="left"><ul><li>Formuler des recommandations lors de la phase de découverte sur les processus d’adoption et de formation</li>
<li>Participer à l’atelier sur la stratégie d’adoption</li>
<li>Développer et être responsable de la stratégie d’adoption</li>
<li>Développer et exécuter le plan de communication</li>
<li>Chargé de dispenser des formations aux utilisateurs finaux</li>
<li>Recueillir les commentaires et réaliser des enquêtes</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Directeur de réseau</strong></td>
<td align="left"><ul><li>Formuler des recommandations lors de la phase de découverte sur la conception du réseau</li>
<li>Participer à la planification lors de l’atelier sur la planification</li>
<li>Coordonner le travail de l’équipe de mise en réseau lors de l’exécution du projet</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Directeur de la sécurité</strong></td>
<td align="left"><ul><li>Formuler des recommandations lors de la phase de découverte sur les processus et la conception de la sécurité</li>
<li>Participer à la planification lors de l’atelier sur la planification</li>
<li>Coordonner le travail de l’équipe chargée de la sécurité lors de l’exécution du projet</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Directeur de la téléphonie</strong></td>
<td align="left"><ul><li>Formuler des recommandations lors de la phase de découverte sur la conception de la téléphonie</li>
<li>Participer à la planification lors de l’atelier sur la planification</li>
<li>Coordonner le travail de l’équipe chargée de la téléphonie lors de l’exécution du projet</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Directeur de bureau</strong></td>
<td align="left"><ul><li>Formuler des recommandations lors de la phase de découverte sur les clients et le processus de mise à jour</li>
<li>Participer à la planification lors de l’atelier sur la planification</li>
<li>Coordonner le travail de l’équipe chargée des bureaux lors de l’exécution du projet</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Accompagner/aider le directeur de bureau</strong></td>
<td align="left"><ul><li>Formuler des recommandations lors de la phase de découverte sur le modèle opérationnel et de prise en charge</li>
<li>Participer à la planification lors de l’atelier sur la planification</li>
<li>Participer à la planification du modèle de prise en charge</li>
<li>Coordonner le travail de l’équipe chargée de la prise en charge/des ressources lors de l’exécution du projet</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Représentants d’unité commerciale</strong></td>
<td align="left"><ul><li>Contribuer aux guides et supports d’adoption basés sur les utilisateurs finaux</li>
<li>Évaluer et contribuer aux cas d’utilisation professionnelle</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Directeur du déploiement</strong></td>
<td align="left"><ul><li>S’assurer que les conditions préalables au déploiement sont remplies</li>
<li>Impliquer des ressources des clients dans l’affectation, la préparation et le déploiement des activités de l’étape</li>
<li>Participer à des réunions pour évaluer l’état de préparation et du déploiement</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Administrateurs informatiques</strong></td>
<td align="left"><ul><li>Spécialistes des technologies de l'information pour aider à la planification et l’exécution des tests</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Propriétaire de service</strong></td>
<td align="left"><ul><li>Responsable du fonctionnement de l’ensemble du service d’audioconférence</li>
<li>Propriétaire du service d’audioconférence</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Ambassadeur de la qualité</strong></td>
<td align="left"><ul><li>Génère des commentaires sur la qualité, la fiabilité et des utilisateurs</li>
<li>Identifie les tendances en matière de qualité et génère les corrections avec les équipes respectives</li>
<li>Fait des rapports par le biais du comité de pilotage à la direction</li>
<li>Fait des rapports sur la qualité, la fiabilité et l’opinion des utilisateurs par l’intermédiaire de Rate My Call et de Net Promoter Score</li></ul></td>
<td align="left">TBA</td>
</tr>
</tbody>
</table>

_Tableau 2 - exemple de modèle de matrice des parties prenantes_


> [!NOTE]
> Le tableau d’exemple ci-dessus et les tableaux suivants dans ce document sont utilisés comme modèle « TBA » (à ajouter) est affiché en regard des informations que vous devez remplir dans le cadre de votre processus de planification.



<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a>Définir les objectifs et les résultats clés, les indicateurs de succès clés et les risques
--------------------------------------------------------------------

Avec les parties prenantes impliquées dans le projet réunies, les cas d’utilisation professionnelle, la portée organisationnelle et le planning du projet peuvent être transposés en objectifs et résultats clés et les mesures de réussite du projet peuvent être définies dans une liste d’indicateurs de succès clés.

L’entière participation des parties prenantes impliquées dans le projet lors de la définition des objectifs et résultats clés et des indicateurs de succès clés garantira le sentiment d’appartenance et qu'ils correspondent aux besoins de l’entreprise en matière d’organisation.

Les objectifs et résultats clés contiennent la liste des objectifs définis au début du projet, les résultats clés mesurables étant définis chaque trimestre. Les résultats clés sont vérifiés chaque mois pour effectuer le suivi du projet global et, en fonction de l’évolution, les plans trimestriels peuvent être adaptés lorsque cela est nécessaire.

<table>
<thead>
<tr class="header">
<th align="left"><p><strong>Vision</strong> : augmenter la productivité an optimisant les investissements dans Office 365</p>
</th>
<th align="left"></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Objectifs</strong></td>
<td align="left"><strong>Résultats clés</strong></td>
<td align="left"><strong>Action</strong></td>
</tr>
<tr class="even">
<td align="left">Déployer l’audioconférence dans Teams d’ici la fin de l’exercice fiscal 2018</td>
<td align="left">T1 de l’exercice 2018 : déployer l’audioconférence dans Teams globalement</td>
<td align="left"><p>Concevoir</p>
<ul><li>Créer un plan de réussite</li>
<li>Créer un plan d’implémentation technique détaillé</li></ul>
<p>Intégrer</p>
<ul><li>Exécuter le plan de réussite</li>
<li>Exécuter le plan d’implémentation technique</li></ul></td>
</tr>
<tr class="odd">
<td align="left">Désactiver l’ancien service de conférence PSTN à l’échelle globale d'ici la fin de l’exercice fiscal 2018</td>
<td align="left">T2 de l’exercice 2018 : désactiver l’ancien service de conférence PSTN à l’échelle globale</td>
<td align="left"><p>Générer une valeur ajoutée</p>
<ul><li>Favoriser l’implication des utilisateurs et encourager l'adoption</li>
<li>Gérer et préparer le changement</li>
<li>Mesurer, partager la réussite et retravailler</li></ul></td>
</tr>
</tbody>
</table>

_Tableau 3 - exemple d’objectifs et résultats clés_


Les indicateurs de succès clés mesurent la qualité et la réussite des résultats clés et complètent la nature binaire des objectifs et résultats clés (obtenus ou non), en détaillant les bons et les mauvais résultats. Lors de la définition des indicateurs de réussite clés, nous recommandons d’utiliser les critères « spécifique, mesurable, attribuable, réaliste, temporel » ou SMART.

<table>
<thead>
<tr class="header">
<th align="left">Type</th>
<th align="left"><p>Questions d’indicateurs de réussite clés &amp;</p>
<p>critères</p></th>
<th align="left">Comment les mesurer</th>
<th align="left">Critères de réussite</th>
<th align="left">Mesurés</th>
<th align="left">Responsable</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Utilisation/adoption</strong></td>
<td align="left">La qualité des appels est égale ou meilleure qu’avec la solution précédente</td>
<td align="left">Enquête</td>
<td align="left">80 % des utilisateurs sont d’accord ou tout à fait d’accord</td>
<td align="left">Après activation et chaque trimestre</td>
<td align="left">Équipe responsable des technologies de l’information</td>
</tr>
<tr class="even">
<td align="left"><strong>Utilisation/adoption</strong></td>
<td align="left">Les équipes ont facilité le processus de communication</td>
<td align="left">Enquête</td>
<td align="left">80 % des utilisateurs sont d’accord ou tout à fait d’accord</td>
<td align="left">Après activation et chaque trimestre</td>
<td align="left">Équipe responsable de la gestion des changements</td>
</tr>
<tr class="odd">
<td align="left"><strong>Utilisation/adoption</strong></td>
<td align="left">Les utilisateurs utilisent activement la solution</td>
<td align="left">Rapports Office 365, tableau de bord de la qualité des appels</td>
<td align="left">80 % des utilisateurs l’utilisent quotidiennement</td>
<td align="left">Chaque jour</td>
<td align="left">Équipe responsable de la gestion des changements</td>
</tr>
<tr class="even">
<td align="left"><strong>Utilisation/qualité</strong></td>
<td align="left">Le pourcentage d’appels/conférences médiocres doit être minimal</td>
<td align="left">Tableau de bord de la qualité des appels</td>
<td align="left">&lt; 5 % d’appels médiocres par mois</td>
<td align="left">Chaque jour</td>
<td align="left">Équipe responsable des technologies de l’information</td>
</tr>
<tr class="odd">
<td align="left"><strong>Utilisation/support</strong></td>
<td align="left">Je sais comment obtenir le support technique</td>
<td align="left">Enquête</td>
<td align="left">90% des utilisateurs sont d’accord ou tout à fait d’accord</td>
<td align="left">Après activation et chaque trimestre</td>
<td align="left">Équipe responsable de la gestion des changements</td>
</tr>
<tr class="even">
<td align="left"><strong>Utilisation/support</strong></td>
<td align="left">Je suis satisfait de la qualité du support technique</td>
<td align="left">Enquête</td>
<td align="left">80 % des utilisateurs sont d’accord ou tout à fait d’accord</td>
<td align="left">Après chaque incident</td>
<td align="left">Équipe responsable des technologies de l’information</td>
</tr>
<tr class="odd">
<td align="left"><strong>Financier</strong></td>
<td align="left">Réduction du nombre de minutes de conférence héritée</td>
<td align="left">Système financier</td>
<td align="left">Atteindre le retour sur investissement défini</td>
<td align="left">Basé sur le retour sur investissement</td>
<td align="left">Équipe responsable de la gestion des changements</td>
</tr>
</tbody>
</table>

_Tableau 4 - exemple d’indicateurs de réussite clés_


Vous devez identifier les risques d’entreprise dans le cadre de cette activité et définir un plan d’atténuation pour chaque risque identifié. Ces informations peuvent être consignées dans un plan de gestion des risques

<table>
<thead>
<tr class="header">
<th align="left">Risque</th>
<th align="left">Probabilité</th>
<th align="left">Impact</th>
<th align="left">Global</th>
<th align="left">Plan d’atténuation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Une fusion prochaine ajoutera jusqu’à 1000 personnes</td>
<td align="left">Élevée</td>
<td align="left">Élevée</td>
<td align="left">Élevée</td>
<td align="left"><p>Pour les entreprises ayant fusionné, différenciez l’objectif et résultat clé avec le processus propre (Planifier, Intégrer, Générer une valeur ajoutée)</p>
<p>Ne les incluez pas dans les objectifs et résultats clés existants</p></td>
</tr>
<tr class="even">
<td align="left">Le transfert des numéros de téléphone retardera la réalisation du projet</td>
<td align="left">Élevée</td>
<td align="left">Élevée</td>
<td align="left">Élevée</td>
<td align="left"><p>Préparer toutes les informations nécessaires pour prendre en charge le transfert des numéros de téléphone au préalable (enregistrement de service client, informations de facturation, courrier d’autorisation)</p>
<p>Ajuster le planning du projet pour concilier la durée de bouclage de l’exécution du transfert des numéros de téléphone</p>
<p>Communiquer l’utilisation de nouveaux numéros de conférence rendez-vous aux participants externes</p></td>
</tr>
<tr class="odd">
<td align="left">Reconception du réseau planifiée</td>
<td align="left">Élevée</td>
<td align="left">Moyenne</td>
<td align="left">Moyenne</td>
<td align="left">Avant d’implémenter Teams comme plate-forme de communication et de collaboration moderne, exécuter l’évaluation de la préparation du réseau pour les sites dans le champ du projet</td>
</tr>
</tbody>
</table>

_Tableau 5 - exemple de plan de gestion des risques_


<a name="assess-environment-and-evaluate-adoption-readiness"></a>Évaluer l'environnement et la préparation à l'adoption
--------------------------------------------------

Pour atteindre les objectifs et résultats clés, vous devez définir l’architecture globale de la solution. Évaluer tous les aspects relatifs à l’infrastructure informatique et de téléphonie, à la mise en réseau et aux opérations nécessite une découverte de l’environnement.

Toutes les questions liées à l’environnement informatique des utilisateurs finaux, tels que l’évaluation de la préparation des ordinateurs personnels et appareils mobiles pour prendre en charge les cas d’utilisation professionnelle de l’audioconférence, de la configuration matérielle requise à la configuration logicielle requise, seront incluses dans le cadre de la découverte de l’environnement.

La découverte de l’environnement peut également révéler s’il existe des exigences relatives au [transfert des numéros de téléphone à Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e). Cela permettra à votre organisation d’ajuster le plan du projet en conséquence et de préparer les infirmations nécessaires pour le transfert des numéros. Vous pouvez effectuer la découverte de l’environnement en utilisant le [questionnaire](https://go.microsoft.com/fwlink/?linkid=858995) suivant.

La découverte de l’environnement doit inclure l’évaluation de la préparation du réseau pour s’assurer que celui-ci est prêt à prendre en charge l’implémentation du service d’audioconférence.

La préparation du réseau pour prendre en charge le service d’audioconférence peut être déterminée en utilisant les informations capturées par le biais de la découverte de l’environnement (comme les informations sur la connectivité Internet et la topologie du réseau étendu, les liens de sites, la bande passante disponible et les données d’analyse des personnes (qui peuvent être converties en utilisation prévue de chaque charge de travail) dans l’outil [My Advisor Network Planner](https://go.microsoft.com/fwlink/?linkid=858999). Pour confirmer la préparation du réseau, une simulation du trafic en temps réel peut être effectuée à l’aide des solutions fournies par [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) ou par les [partenaires d'outils d’évaluation de la préparation du réseau](https://go.microsoft.com/fwlink/?linkid=859003).

Les résultats de l’évaluation de la préparation du réseau donneront une image plus claire de l’optimisation du réseau nécessaire ou de la correction requise pour réussir l’implémentation de l’audioconférence.

La préparation à l’adoption peut être évaluée en exécutant une analyse des personnes qui établira une liste des personnes dans l'organisation qui peuvent être ciblées pour l’implémentation du service d’audioconférence. L’analyse des personnes inclut l’identification des périphériques ou dispositifs requis pour aboutir aux résultats de l’entreprise attendus.

Pour effectuer une analyse des personnes, vous pouvez organiser un atelier en impliquant les parties prenantes impliquées dans le projet, à l’aide du support d’atelier [Alignement des personnes](https://go.microsoft.com/fwlink/?linkid=859005) et de la [Matrice des fonctionnalités des personnes](https://go.microsoft.com/fwlink/?linkid=859006). Le résultat de l’atelier d’analyse des personnes peut être résumé dans un rapport à l’aide du modèle [Rapport d’analyse des personnes](https://go.microsoft.com/fwlink/?linkid=859007).


> [!NOTE]
> Les exemples de questionnaire de découverte et d’analyse des personnes ont été rédigés initialement pour Skype Entreprise Online, mais la plus grande partie du contenu s’applique à Teams. N’hésitez pas à modifier et supprimer les éléments non pertinents par rapport aux objectifs du projet.


Vous pouvez identifier les risques techniques dans le cadre de l’évaluation de l’environnement et de la préparation à l’adoption et élaborer un plan d’atténuation pour chaque risque identifié. Ces informations doivent être incorporées dans le plan de gestion des risques.

<a name="map-operational-roles"></a>Mapper les rôles opérationnels
---------------------

La planification des opérations et l identification des équipes qui utiliseront le service d’audioconférence sont une étape importante, les opérations devant commencer lorsque les premiers utilisateurs pilotes sont activés. Chaque équipe identifiée doit vérifier et contenir des tâches et responsabilités identifiées et commencer la préparation pour utiliser le service d’audioconférence. La préparation doit inclure la formation et la préparation, le personnel supplémentaire ou s’assurer que les fournisseurs externes sont configurés pour fournir le service.

<table>
<thead>
<tr class="header">
<th align="left">Rôle opérationnel</th>
<th align="left">Description</th>
<th align="left">Équipe</th>
<th align="left">Détails du contact</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Propriétaire de service</td>
<td align="left">Propriétaire de service, interface avec les divisions de l’entreprise, stratégie</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">Opérations d’audioconférence</td>
<td align="left">Opérations quotidiennes, déplacement/ajout/modification des comptes d’utilisateurs et d’appareils, supervision</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">Administration des clients</td>
<td align="left">Modifier les paramètres à l'échelle du client, activer les nouvelles fonctions</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">Support technique</td>
<td align="left">Interface permettant aux utilisateurs finaux d’obtenir un support</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">Opérations réseau</td>
<td align="left">Exécution du réseau local, étendu, Wi-Fi et accès à Internet</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">Équipe responsable des points de terminaison &amp; de client</td>
<td align="left">Gérer les déploiements de bureau</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">Opérations d’identité</td>
<td align="left">Gérer l’infrastructure d’identité (AD, ADFS, Azure AD)</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">Adoption/gestion des changements</td>
<td align="left">Gérer la sensibilisation, la formation et l’adoption de la solution</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">Opérations Exchange</td>
<td align="left">Gère l’environnement Exchange</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
</tbody>
</table>

_Tableau 6 - exemple de mappage des rôles opérationnels_


Pour permettre un mappage des rôles opérationnels plus détaillé, incluant les tâches associées à chaque rôle opérationnel, vous pouvez utiliser le [Classeur de mappage des rôles opérationnels](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) pour capturer les détails qui permettront d’avoir une vision claire des rôles et responsabilités pour la prise en charge du service d’audioconférence.

<a name="document-success-plan"></a>Documenter le plan de réussite
---------------------

Un plan de réussite est une documentation créée dans la phase Planifier constituée d'un script commercial, de la préparation du service, d'un plan d’adoption et d’un plan opérationnel.

Le plan de réussite fournira l’équipe du projet, qui peut inclure FastTrack ou un partenaire de déploiement, avec des informations suffisantes pour réaliser les objectifs de l’organisation avec le service d’audioconférence.

Généralement, un plan de réussite contiendra les sections principales suivantes :

-   Script commercial

-   Préparation du service

-   Plan d’adoption

-   Plan opérationnel

### <a name="business-case"></a>Script commercial

Les cas d’utilisation professionnelle, les parties prenantes, les objectifs et résultats clés et les indicateurs de réussite clés, les risques et le planning du projet constituent généralement l’essentiel des informations nécessaires pour un script commercial. Vous devez les documenter dans le cadre du plan de réussite.

### <a name="service-readiness"></a>Préparation du service

L’évaluation de l’environnement fournit les informations initiales nécessaires pour déterminer la préparation technique de l’organisation pour implémenter l’audioconférence.

Le plan pour régler les éléments nécessitant une correction découverts par le biais de l’évaluation de l’environnement est inclus ici. Vous devez inclure l’évaluation de la préparation du service et le plan de correction au plan de réussite.

### <a name="adoption-plan"></a>Plan d’adoption

Après l’évaluation de la préparation à l’adoption, une planification plus détaillée doit être fournie pour que l’équipe du projet puisse générer un ensemble complet de plans de communication, un plan de formation et des activités d’adoption avant, pendant et après le lancement.

Les ressources permettant d’appuyer les activités liées à l’adoption sont des prospectus, des courriers électroniques de bienvenue et les supports de formation identifiés dans cette étape, ainsi que les personnalisations nécessaires pour répondre aux besoins de l'organisation.

Les modèles d’activités d’adoption sont disponibles [ici](https://www.microsoft.com/download/details.aspx?id=54244).

### <a name="operational-plan"></a>Plan opérationnel

L’activité de mappage des rôles opérationnels établira les rôles et les responsabilités, ainsi que les équipes affectées à chaque rôle opérationnel pour prendre en charge l’implémentation de l’audioconférence.

Vous devez effectuer cette étape et inclure le plan opérationnel dans le plan de réussite pour garantir la préparation opérationnelle de la solution.

Planification de l’audioconférence dans Teams  <a name="Planning_AudioConferencing"> </a>
========================================

Pour planifier l’implémentation de l’audioconférence dans Teams, une série de décisions doivent être prises au préalable afin de mieux préparer votre organisation à implémenter une solution qui répond aux besoins de l’entreprise. Ces décisions seront documentées dans un plan d’implémentation technique.

|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AWbuvcWcYIc" frameborder="0" allowfullscreen></iframe>    | |


## <a name="availability-of-audio-conferencing"></a>Disponibilité de l’audioconférence

L’audioconférence est disponible dans les [pays et régions suivants :](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US).


> [!IMPORTANT]
> En raison de contraintes juridiques, pour que l’audioconférence soit disponible dans les organisations multinationales, le contrat des abonnements Office 365 doit souscrit dans les pays et régions couverts par le service d’audioconférence.

Après avoir vérifié l’admissibilité de votre organisation à obtenir le service d’audioconférence, établissez la liste des emplacements des utilisateurs ou des bureaux où le service d’audioconférence sera implémenté en vous basant sur la liste des pays et régions disponibles.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Points de décision</td>
<td align="left"><p>Déterminez les emplacements des utilisateurs ou les bureaux qui implémenteront le service d’audioconférence.</p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Étapes suivantes</td>
<td align="left"><p>Consignez les emplacements des utilisateurs ou les bureaux qui seront habilités pour le service d’audioconférence.</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Bureau</th>
<th align="left">Emplacement</th>
<th align="left">Service de conférence PSTN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1 Eppîng Road</td>
<td align="left">Australie</td>
<td align="left">Audioconférence</td>
</tr>
<tr class="even">
<td align="left">100 Cyberport Road</td>
<td align="left">Hong Kong R.A.S.</td>
<td align="left">Conférence PSTN héritée</td>
</tr>
<tr class="odd">
<td align="left">1 Marina Boulevard</td>
<td align="left">Singapour</td>
<td align="left">Audioconférence</td>
</tr>
<tr class="even">
<td align="left">32 London Bridge Street</td>
<td align="left">Royaume-Uni</td>
<td align="left">Audioconférence</td>
</tr>
<tr class="odd">
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">France</td>
<td align="left">Audioconférence</td>
</tr>
</tbody>
</table>

_Tableau 7 - exemple de liste d’habilitations de sites pour le service d’audioconférence_


## <a name="licensing-for-audio-conferencing"></a>Licences pour l’audioconférence

[La licence pour l’audioconférence](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US), appelée auparavant Licence de conférence PSTN Skype Entreprise, est disponible dans le cadre des plans d’abonnement Office 365 E5, ou en tant que complément des plans d’abonnement Office 365 E1 ou Office 365 E3.

> [!NOTE]
> La conférence PSTN ou rendez-vous dans Teams ne prend pas en charge les<sup></sup>-fournisseurs de service d’audioconférence tiers (ACP). <br>Si vous utilisez déjà la conférence PSTN Skype Entreprise Online, vous pouvez bénéficier immédiatement de l’audioconférence dans Teams.

Pour fournir des numéros gratuits de pont de téléconférence et pour prendre en charge les appels de téléconférence vers des numéros internationaux, vous devez configurer des [crédits de communication](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) pour votre organisation.


> [!IMPORTANT]
> Certains pays sont desservis uniquement par des numéros gratuits de téléconférence et, dans ce cas, l’utilisation de crédits de communication est obligatoire pour prendre en charge la composition de numéros pour ces pays.

Le premier élément à prendre en compte lors de l’implémentation de crédits de communication est de décider du montant initial des fonds à acheter. Les montants de financement recommandés peuvent être obtenus dans la documentation sur les [crédits de communication](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059).

Si votre organisation choisit d’utiliser la recharge automatique, une recommandation sur le déclencheur (montant des fonds le moins élevé) est également incluse dans la documentation sur les [crédits de communication](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059). Le montant de la recharge automatique doit être déterminé par l’utilisation réelle. L’utilisation des crédits de communication doit être contrôlée au fil du temps et le montant de la recharge doit être ajusté en fonction des besoins.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Points de décision</td>
<td align="left"><ul><li>Si votre organisation n’a pas déjà acheté les licences requises pour l’audioconférence, déterminez si les licences seront acquises en passant à des niveaux d’abonnement Office 365 supérieurs ou en achetant des compléments pour l’audioconférence.</li>
<li>Déterminez si des crédits de communication sont requis pour l’implémentation de l’audioconférence. Si c’est le cas, déterminez le montant initial des fonds qui doit être acheté. Le cas échéant, déterminez le montant déclencheur et celui de la recharge automatique.</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Étapes suivantes</td>
<td align="left"><ul><li>Consignez les utilisateurs à qui une licence d’audioconférence sera attribuée.</li>
<li>Documentez le plan de crédits de communication (montant initial, montant déclencheur, montant de la recharge automatique).</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Utilisateur</th>
<th align="left">Bureau</th>
<th align="left">Licence Office 365</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">1 Eppîng Road</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">1 Eppîng Road</td>
<td align="left">Office 365 E3, complément pour l’audioconférence</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">1 Eppîng Road</td>
<td align="left">Office 365 E3, complément pour l’audioconférence</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">1 Marina Boulevard</td>
<td align="left">Office 365 E3, complément pour l’audioconférence</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">1 Marina Boulevard</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">1 Marina Boulevard</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E3, complément pour l’audioconférence</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E3, complément pour l’audioconférence</td>
</tr>
</tbody>
</table>

_Tableau 8 - exemple de liste d’attributions de licences pour les organisateurs de réunions en audioconférence_

<table>
<thead>
<tr class="header">
<th align="left">Montant initial</th>
<td align="left">1 000 $</td>
</tr>
</thead>
<thead>
<tr class="header">
<th align="left">Montant déclencheur</th>
<td align="left">400 $</td>
</tr>
<tr class="header">
<th align="left">Montant de la recharge automatique</th>
<td align="left">TBA</td>
</tr>
</tbody>
</table>

_Tableau 9 - exemple de numéros de planification de crédits de communication_


## <a name="conference-bridge-phone-numbers"></a>Numéros de pont de téléconférence

Le service d’audioconférence dans Office 365 inclut les éléments suivants :

-   plusieurs types de numéros de pont de téléconférence (payants et gratuits) ;

-   plusieurs catégories de numéros de téléphone (dédiés et partagés) ;

-   prise en charge de plusieurs langues pour le pont de téléconférence (principale et secondaire) ;

-   numéro de téléphone par défaut du client.

Vous trouverez une description complète des fonctionnalités incluses dans les rubriques [Configurer la conférence rendez-vous ou PSTN dans Skype Entreprise](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) et [Numéros de téléphone pour la conférence rendez-vous](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**

> [!NOTE]
> Les numéros de pont de téléconférence dédiés sont inclus dans le calcul de la limite du nombre de numéros de téléphone qui peuvent être achetés par client, en fonction du nombre de licences applicables comme il est décrit dans la rubrique [Obtenir des numéros de téléphone du service Skype Entreprise](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734). Les numéros de pont de téléconférence gratuits requièrent des crédits de communication.

Si des numéros de pont de téléconférence existants doivent être transférés vers le service d’audioconférence, en partant du principe qu'ils répondent aux exigences spécifiques au pays, ils peuvent être transférés vers Microsoft.


> [!NOTE]
> Le transfert de numéros de téléphone vers Microsoft est plus ou moins complexe selon les pays ou régions, les opérateurs, le nombre de circuits concernés et de nombreux autres facteurs. Pour planifier un transfert de numéros de téléphone, consultez le [Guide de transfert de numéros](https://go.microsoft.com/fwlink/?linkid=859011).

|  |  |
|---------|---------|
| <iframe width="350" height="200" src="https://www.youtube.com/embed/5k0C21KAsns" frameborder="0" allowfullscreen></iframe>  |  |

Vous trouverez des informations complémentaires sur le transfert de numéros de téléphone vers le service d’audioconférence dans la rubrique [Transférer des numéros de téléphone vers Skype Entreprise Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Points de décision</td>
<td align="left"><ul><li>Déterminer si l’organisation a besoin de numéros de pont de téléconférence dédiés</li>
<li>Déterminer comment les numéros de pont de téléconférence dédiés seront obtenus pour les emplacements des utilisateurs ou les bureaux concernés par l’implémentation de l’audioconférence (les obtenir auprès de Microsoft ou transférer des numéros de téléphone existants)</li>
<li>Si vous choisissez de les obtenir auprès de Microsoft, décider de la méthode pour les obtenir (envoi de formulaire ou automatisé) pour les emplacements des utilisateurs ou les bureaux concernés par l’implémentation de l’audioconférence</li>
<li>Déterminer les préférences de langue à configurer pour chaque numéro de pont de téléconférence dédié</li>
<li>Décider du numéro de pont de téléconférence par défaut du client</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Étapes suivantes</td>
<td align="left"><ul><li>Documentez le plan général d’acquisition de numéros de téléphone, en détaillant comment les numéros de téléphone seront obtenus pour chaque emplacement d’utilisateur ou bureau concernés par l’implémentation de l’audioconférence.</li>
<li>Le cas échéant, remplir <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">le formulaire de demande de nouveau numéro de téléphone</a> (un formulaire par emplacement ou bureau)</li>
<li>Si vous choisissez de transférer des numéros de téléphone existants, consultez le <a href="https://go.microsoft.com/fwlink/?linkid=859011">Guide de transfert de numéros</a> pour le planifier et ajuster le planning d’implémentation de l’audioconférence en conséquence.</li>
<li>Documenter les configurations détaillées des numéros de pont de téléconférence (numéros de pont de téléconférence partagés et dédiés, préférences de langue pour chaque numéro de pont de téléconférence dédié, numéro de pont de téléconférence par défaut du client)</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Bureau</th>
<th align="left">Acquisition de numéro de pont de téléconférence et type de pont</th>
<th align="left">Numéro du pont</th>
<th align="left">Langue du pont</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1 Eppîng Road</td>
<td align="left">Acquisition d'un nouveau numéro de pont dédié</td>
<td align="left">TBA</td>
<td align="left">Anglais (Australie)</td>
</tr>
<tr class="even">
<td align="left">1 Marina Boulevard</td>
<td align="left">Acquisition d'un nouveau numéro de pont partagé</td>
<td align="left">TBA</td>
<td align="left">Anglais (États-Unis), Chinois (simplifié, RPC)</td>
</tr>
<tr class="odd">
<td align="left">32 London Bridge Street</td>
<td align="left">Port existant, dédié</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">Anglais (Royaume-Uni)</td>
</tr>
<tr class="even">
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Acquisition d'un nouveau numéro de pont dédié</td>
<td align="left">TBA</td>
<td align="left">Français (France), Anglais (Royaume-Uni)</td>
</tr>
</tbody>
</table>

_Tableau 10 - exemple de détails de pont de téléconférence_


> [!NOTE]
> Le tableau d’exemple ci-dessus et les tableaux suivants dans ce document sont utilisés comme modèle « TBA » (à ajouter) est affiché en regard des informations que vous devez remplir dans le cadre de votre processus de planification.

## <a name="conference-bridge-settings"></a>Paramètres du pont de téléconférence

Des options de configuration à l’échelle de l’organisation relatives à l’expérience de participation aux réunions en audioconférence (notification d’accès et de sortie de réunion et enregistrement du numéro de l’appelant), à la longueur du code PIN des organisateurs de réunion et à la notification par courrier électronique sont disponibles afin de personnaliser davantage l’expérience des utilisateurs finaux.

-   Les notifications d’accès et de sortie de réunion sont disponibles sous la forme de nom enregistré, de numéro de téléphone et de tonalités.

-   La longueur du code PIN peut être configurée entre 4 et 12 chiffres, un code PIN de 5 chiffres étant configuré par défaut.

-   Les notifications par courrier électronique lors de l’activation d'une licence d’audioconférence ou d’autres modifications effectuées par un administrateur sont activées par défaut. Vous pouvez désactiver cette fonction et contrôler les communications des utilisateurs finaux de votre organisation.

Pour les utilisateurs à qui une licence d’audioconférence a été attribuée, les numéros payants/gratuits, présentés dans les coordonnées d’audioconférence, peuvent être configurés pour utiliser :

-   le numéro par défaut au niveau du client, ou

-   les numéros de pont de téléconférence attribués automatiquement, ou

-   des numéros de pont de téléconférence définis manuellement pour chaque utilisateur.

Des numéros de pont de téléconférence spécifiques aux utilisateurs sont généralement utiles dans les organisations mondiales ou à l'échelle du pays ou de la région où les utilisateurs sont distribués et doivent fournir des numéros locaux comme numéros de pont de téléconférence par défaut dans les invitations aux réunions.

Les participants qui rejoignent les réunions depuis des villes ou pays différents peuvent rechercher les numéros supplémentaires configurés au niveau du client, mais ces numéros n’apparaissent pas dans les invitations aux réunions. Les invitations aux réunions fournissent un lien qui dirige les participants vers la page des numéros à composer pour la conférence Teams afin qui leur permet de rechercher les numéros de pont de téléconférence les plus proches disponibles pour leur emplacement.

Vous pouvez également configurer comment les utilisateurs non authentifiés sont gérés par chaque organisateur de réunion individuel : exiger que l’organisateur de la réunion commence la réunion avant que les appelants non authentifiés soient admis ou autoriser les appelants non authentifiés à démarrer une réunion.

Des configurations supplémentaires pouvant être appliquées pour chaque utilisateur sont disponibles pour contrôler l’utilisation de numéros de pont de téléconférence gratuits et les appels depuis une conférence.

> [!NOTE]
> Ces contrôles liés au coût ne sont disponibles actuellement que pour les utilisateurs précoces. Vous pouvez inscrire votre organisation au programme d’évaluation depuis la page [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).

Ces contrôles vous permettent de déterminer si les organisateurs de réunions peuvent fournir des numéros de pont de téléconférence gratuits pour les réunions qu’ils organisent, et de contrôler si les participants peuvent composer des numéros depuis les réunions qu'ils ont organisées. Les niveaux de contrôle sont les suivants : ne pas autoriser la composition de numéros, autoriser uniquement la composition de numéros nationaux, autoriser la composition de numéros nationaux et internationaux.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Points de décision</td>
<td align="left"><ul><li>Déterminez si l’organisation requiert des notifications d’accès et de sortie de réunion et, le cas échéant, le type de notification à implémenter (tonalités, numéro de téléphone ou nom enregistré).</li>
<li>Déterminez la longueur du code PIN pour l’audioconférence qui correspond aux exigences de sécurité de l'organisation.</li>
<li>Déterminez si l’organisation souhaite contrôler les communications des utilisateurs finaux liées au service d’audioconférence.</li>
<li>Déterminez les numéros de pont de téléconférence à attribuer à chaque organisateur de réunions.</li>
<li>Déterminez si certains organisateurs de réunions doivent pouvoir utiliser des numéros de pont de téléconférence gratuits pour leurs réunions.</li>
<li>Déterminez si certains organisateurs de réunions doivent pouvoir autoriser les appelants non authentifiés à démarrer une réunion.</li>
<li>Déterminez si la composition des numéros doit être contrôlée pour certains organisateurs de réunions.</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Étapes suivantes</td>
<td align="left"><ul><li>Consignez les paramètres détaillés de pont de téléconférence (notifications d’accès et de sortie de réunion, longueur du code PIN, notification par courrier électronique des modifications de configuration).</li>
<li>Consignez les numéros de pont de téléconférence qui seront attribués à chaque organisateur de réunions et le paramètre correspondant de la stratégie de contrôle des appelants non authentifiés et pour les numéros gratuits et les appels.</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><strong>Activer les notifications d’accès et de sortie de réunion</strong></td>
<td align="left">Activé</td>
</tr>
</thead>
<thead>
<tr class="header">
<td align="left"><strong>Type d’annonce d’accès/sortie</strong></td>
<td align="left">Tonalités</td>
</tr>
<tr class="header">
<td align="left"><strong>Demander aux appelants d’enregistrer leur nom avant de rejoindre la réunion</strong></td>
<td align="left">Désactivé</td>
</tr>
<tr class="header">
<td align="left"><strong>Longueur du code PIN</strong></td>
<td align="left">5</td>
</tr>
<tr class="header">
<td align="left"><strong>Envoyer automatiquement des e-mails aux utilisateurs si leurs paramètres de numérotation changent</strong></td>
<td align="left">Désactivé</td>
</tr>
</tbody>
</table>

_Tableau 11 - exemple de paramètres de pont de téléconférence_


<table>
<thead>
<tr class="header">
<th align="left">Utilisateur</th>
<th align="left">Bureau</th>
<th align="left">Numéro payant par défaut</th>
<th align="left">Numéro gratuit par défaut</th>
<th align="left">Autoriser le numéro gratuit</th>
<th align="left">Les appelants non authentifiés contournent la salle d’attente</th>
<th align="left">Composition de numéros depuis la conférence</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">1 Eppîng Road</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Oui</td>
<td align="left">Activé</td>
<td align="left">Internationaux et nationaux</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">1 Eppîng Road</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Non</td>
<td align="left">Désactivé</td>
<td align="left">Non autorisé</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">1 Eppîng Road</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Non</td>
<td align="left">Désactivé</td>
<td align="left">Non autorisé</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">1 Marina Boulevard</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Oui</td>
<td align="left">Désactivé</td>
<td align="left">Nationaux</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">1 Marina Boulevard</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Oui</td>
<td align="left">Activé</td>
<td align="left">Nationaux</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">1 Marina Boulevard</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Oui</td>
<td align="left">Activé</td>
<td align="left">Nationaux</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">TBA</td>
<td align="left">Oui</td>
<td align="left">Activé</td>
<td align="left">Non autorisé</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">TBA</td>
<td align="left">Oui</td>
<td align="left">Désactivé</td>
<td align="left">Non autorisé</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">TBA</td>
<td align="left">Oui</td>
<td align="left">Désactivé</td>
<td align="left">Non autorisé</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Non</td>
<td align="left">Désactivé</td>
<td align="left">Nationaux</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Oui</td>
<td align="left">Activé</td>
<td align="left">Internationaux et nationaux</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Non</td>
<td align="left">Désactivé</td>
<td align="left">Nationaux</td>
</tr>
</tbody>
</table>

_Tableau 12 - exemple d’affectations de paramètres de pont de téléconférence_


## <a name="dial-plans"></a>Plan de numérotation

Un [Plan de numérotation](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b), une fonctionnalité de système téléphonique d’Office 365, est un ensemble de règles de normalisation qui convertit les numéros de téléphone composés dans un autre format (généralement le format [E.164](https://go.microsoft.com/fwlink/?linkid=859014)) pour l’autorisation et le routage des appels. Le service d’audioconférence utilise les mêmes fonctionnalités que le système téléphonique pour convertir les numéros de téléphone en scénarios de numéros composés depuis la conférence.

Un plan de numérotation permet aux utilisateurs de composer des numéros de téléphone comme ils le font habituellement, par exemple en omettant l'indicatif régional pour les appels locaux, l'indicatif du pays ou de la région pour les appels nationaux ou même en composant un numéro court lorsqu'ils passent un appel depuis une conférence.

La fonctionnalité de système téléphonique d’Office 365 comporte deux types de plans de numérotation :

-   **Plan de numérotation de service**. Il s’agit du plan de numérotation par défaut, qui est appliqué aux utilisateurs selon l’emplacement d’utilisation d’Office 365, et il ne peut pas être modifié.

<!-- -->

-   **Plan de numérotation de client**. Ce plan de numérotation peut être personnalisé au sein d'un client, et divisé en deux types :

    -   **Plan de numérotation de client global** : ce plan de numérotation s’applique à tous les utilisateurs au sein du client.

    -   **Plan de numérotation d’utilisateurs du client** : ce plan de numérotation s’applique uniquement à des utilisateurs spécifiques.


> [!NOTE]
> Pour des informations détaillées et des exemples, consultez la documentation [Plans de numérotation du forfait d’appels Office 365](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b).

Le plan de numérotation efficace affecté aux utilisateurs est la combinaison du plan de numérotation de service (basé sur l’emplacement d’utilisation d’Office 365 des utilisateurs) et du plan de numérotation de client (il peut s’agir d’un plan de numérotation de client.global ou d'un plan de numérotation d’utilisateurs du client).

![Le tableau présente trois combinaisons de plans de numérotation de client et de service.](media/audio_conferencing_image8.png)

Il existe 25 règles de normalisation au maximum dans chaque plan de numérotation de client, et le double emploi des règles de normalisation déjà disponibles dans le plan de numérotation de service doit donc être évité.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Points de décision</td>
<td align="left"><ul><li>Déterminez si votre organisation requiert des plans de numérotation personnalisés (besoins de l’entreprise, exigences en matière d’adoption, etc.).</li>
<li>Le cas échéant, déterminez la portée du plan de numérotation de client (global au sein du client ou utilisateurs du client) pour prendre en charge les exigences des plans de numérotation personnalisés.</li>
<li>Le cas échéant, déterminez les plans de numérotation de client qui seront créés pour prendre en charge les emplacements des utilisateurs ou les bureaux concernés par l’implémentation de l’audioconférence.</li>
<li>Le cas échéant, déterminez le plan de numérotation personnalisé et le plan de numérotation de client.qui doit être affecté à chaque utilisateur.</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Étapes suivantes</td>
<td align="left"><ul><li>Consignez les plans de numérotation personnalisés et les règles de normalisation associées à configurer dans le cadre de l’implémentation de l’audioconférence.</li>
<li>Consignez les utilisateurs auxquels le plan de numérotation personnalisé sera affecté et le plan de numérotation de client.qui doit être affecté à chaque utilisateur.</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Nom/description du plan de numérotation de client.</th>
<th align="left">Nom/description des règles de normalisation</th>
<th align="left">Modèle</th>
<th align="left">Conversion</th>
<th align="left">IsInternalExtension</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>AU-NSW-NorthRyde-OER</strong></p>
<p><em>1 Epping Road North Ryde, NSW, plan de numérotation AU</em></p></td>
<td align="left"><p><strong>AU-NSW-NorthRyde-OER-Internal</strong></p>
<p><em>Numéro interne (x7000 - x7999) du 1 Epping Road office, North Ryde, NSW, Australie</em></p></td>
<td align="left">^(7\d{3})$</td>
<td align="left">+6125550$1</td>
<td align="left">True</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>AU-NSW-Local</strong></p>
<p><em>Normalisation du numéro local pour NSW, Australie</em></p></td>
<td align="left">^([2-9]\d{7})$</td>
<td align="left">+612$1</td>
<td align="left">False</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>AU-TollFree</strong></p>
<p><em>Normalisation du numéro gratuit pour l’Australie</em></p></td>
<td align="left">^(1[38]\d{4,8})\d*$</td>
<td align="left">+61$1</td>
<td align="left">False</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>AU-Service</strong></p>
<p><em>Normalisation du numéro de service pour l’Australie</em></p></td>
<td align="left">^(000|1[0125]\d{1,8})$</td>
<td align="left">$1</td>
<td align="left">False</td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SG-Singapore-OMB</strong></p>
<p><em>OMB Singapour, plan de numérotation SG</em></p></td>
<td align="left"><p><strong>SG-OMB-Internal</strong></p>
<p><em>Numéro interne (x8000 – x8999) du bureau OMB, Singapour</em></p></td>
<td align="left">^(8\d{3})$</td>
<td align="left">+656888$1</td>
<td align="left">True</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>SG-TollFree</strong></p>
<p><em>Normalisation du numéro gratuit pour Singapour</em></p></td>
<td align="left">^(1?800\d{7})\d*$</td>
<td align="left">+65$1</td>
<td align="left">False</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>SG-Service</strong></p>
<p><em>Normalisation du numéro de service pour Singapour</em></p></td>
<td align="left">^(1\d{3,4}|9\d{2})$</td>
<td align="left">$1</td>
<td align="left">False</td>
</tr>
<tr class="even">
<td align="left"><p><strong>FR-Paris-Issy-39qdPR</strong></p>
<p><em>39 quai du Président Roosevelt Issy-les-Moulineaux, plan de numérotation France</em></p></td>
<td align="left"><p><strong>FR-39qdPR-Internal</strong></p>
<p><em>Numéro interne (x7000 – x7999) du bureau 39 quai du Président Roosevelt, Issy-les-Moulineaux, France</em></p></td>
<td align="left">^(7\d{3})$</td>
<td align="left">+3319999$1</td>
<td align="left">True</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>FR-TollFree</strong></p>
<p><em>Normalisation du numéro gratuit pour la France</em></p></td>
<td align="left">^0?(80\d{7})\d*$</td>
<td align="left">+33$1</td>
<td align="left">False</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>FR-Service</strong></p>
<p><em>Normalisation du numéro de service pour la France</em></p></td>
<td align="left"><p>^(1\d{1,2}|11[68]\d{3}|</p>
<p>10\d{2}|3\d{3})$</p></td>
<td align="left">$1</td>
<td align="left">False</td>
</tr>
</tbody>
</table>

_Tableau 13 - exemple de plans de numérotation de client_


<table>
<thead>
<tr class="header">
<th align="left">Utilisateur</th>
<th align="left">Bureau</th>
<th align="left">Type de plan de numérotation</th>
<th align="left">Nom du plan de numérotation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">1 Eppîng Road</td>
<td align="left">Plan de numérotation de client</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">1 Eppîng Road</td>
<td align="left">Plan de numérotation de client</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">1 Eppîng Road</td>
<td align="left">Plan de numérotation de client</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">1 Marina Boulevard</td>
<td align="left">Plan de numérotation de client</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">1 Marina Boulevard</td>
<td align="left">Plan de numérotation de client</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">1 Marina Boulevard</td>
<td align="left">Plan de numérotation de client</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Plan de numérotation de service</td>
<td align="left">N/A</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Plan de numérotation de service</td>
<td align="left">N/A</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Plan de numérotation de service</td>
<td align="left">N/A</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Plan de numérotation de client</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Plan de numérotation de client</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Plan de numérotation de client</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
</tbody>
</table>

_Tableau 14 - exemple d’affectations de plan de numérotation_


## <a name="microsoft-teams-configurations"></a>Configurations de Microsoft Teams

L’audioconférence n’étant disponible que pour les réunions planifiées, les configurations au niveau du client qui régissent la planification des réunions (réunions privées et de canal) doivent être activées.


> [!NOTE]
> Actuellement, si votre organisation a des exigences de conformité exigeant que toutes les discussions en réunion puissent être découvertes, vous devez désactiver les réunions privées si l’organisateur dispose d’une boîte aux lettres sur site Exchange.<br><br>
> Dans un autre cas d’utilisation, si toutes les réunions dans l’organisation doivent être visibles <strong>pour les parties invitées</strong> uniquement, afin d’empêcher que les informations sur les réunions soient divulguées aux parties non invitées, nous vous recommandons de désactiver la possibilité de planifier des réunions dans les <strong>canaux</strong>.

Les paramètres, disponibles en tant que configurations au niveau du client, s’appliquent à tous les utilisateurs dans l’organisation et auront une incidence sur toutes les planifications de réunions dans Teams, et non pas uniquement aux réunions Teams **avec** l’audioconférence.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Point de décision</td>
<td align="left"><p>Déterminez si l’organisation requiert que la planification de réunions privées soit activée ou désactivée.</p>
<p>Déterminez si l’organisation requiert que la planification de réunions de canal soit activée ou désactivée.</p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Étapes suivantes</td>
<td align="left"><p>Consignez les configurations de planification de réunions de Teams.</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><strong>Autoriser la planification de réunions privées</strong></td>
<td align="left">Activé</td>
</tr>
</thead>
<thead>
<tr class="odd">
<td align="left"><strong>Autoriser la planification de réunions de canal</strong></td>
<td align="left">Désactivé</td>
</tr>
</tbody>
</table>

_Tableau 15 - exemple de configurations de réunions Microsoft Teams_


## <a name="document-technical-implementation-plan"></a>Documenter le plan d’implémentation technique

Utilisez les points de décision ci-dessus pour documenter votre plan d’implémentation technique.

Ce plan d’implémentation technique fournira l’équipe du projet, qui peut inclure FastTrack ou un partenaire de déploiement, avec les informations nécessaires pour exécuter l’intégration technique pour l’implémentation de l’audioconférence.

Généralement, un plan d’implémentation technique contiendra les sections principales suivantes :

-   Liste d’habilitations de sites pour le service d’audioconférence

-   Liste d’attributions de licences pour les organisateurs de réunions en audioconférence

-   Numéros de planification de crédits de communication

-   Détails du pont de téléconférence

-   Paramètres du pont de téléconférence

-   Affectations de paramètres de pont de téléconférence

-   Plans de numérotation de client

-   Affectations du plan de numérotation

-   Configurations des réunions Microsoft Teams

Une fois les plans de réussite et d’implémentation technique établis, vous êtes prêt à faire franchir à votre organisation les étapes suivantes du parcours du client d’Office 365.

<a name="onboard"></a>Intégrer
=======

*Bientôt disponible.*

<a name="drive-value"></a>Générer une valeur ajoutée
===========

*Bientôt disponible.*



### <a name="see-also"></a>Voir aussi
[Configurer la conférence rendez-vous ou PSTN dans Skype Entreprise](https://support.office.com/article/Set-up-audio-conferencing-for-Skype-for-Business-and-Microsoft-Teams-d01954f1-4f37-4cf5-a636-20039e5c59e9)
