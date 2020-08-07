---
title: Insights dans Microsoft Teams pour l’éducation pour les administrateurs informatiques
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Un guide ITAdmin sur Insights dans Microsoft Teams pour l’éducation.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75d9396bf5f537f965493bb0db317a1286b2f950
ms.sourcegitcommit: b14ad0a6c454b20f34fccbd1d312de24379faef0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2020
ms.locfileid: "46572369"
---
# <a name="insights-in-teams-for-education-for-it-admins"></a>Insights dans Teams pour l’éducation pour les administrateurs informatiques

Avec Microsoft Teams pour l’éducation, les enseignants et chefs d’établissement peuvent accéder à des données analytiques sur l’engagement numérique, la charge de travail, les notes, la communication, etc.

Insights est actif dans les SKU A1, A3 et A5 d’Office 365 Éducation.

> [!NOTE]
> Enseignants, découvrez comment utiliser Insights [ici](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc).

## <a name="permissions"></a>Autorisations

- Les étudiants sont identifiés par leur licence et **n’ont pas accès à l’onglet Insights** (même s’ils sont propriétaires de l’équipe).
- Les enseignants sont définis par les licences du corps professoral. Les enseignants doivent disposer d’une licence du corps professoral et être propriétaires d’une équipe de classe pour ajouter et afficher l’onglet Insights. L’onglet reflète les activités des membres de l’équipe de classe qui ne sont pas propriétaires (y compris les enseignants qui ne sont pas propriétaires de l’équipe).
- La définition standard du chef d’établissement consiste en une licence pour le corps professoral. L’administrateur général en informatique est identifié par son rôle. Les chefs d’établissement doivent disposer d’une licence du corps professoral et recevoir des autorisations explicites de l’administrateur général en informatique pour afficher les rapports dans l’application Insights.

Nous proposons Insights sous deux formes :
- Onglets : les enseignants peuvent ajouter Insights à un canal public au sein d’une équipe de classe en accédant aux Applications dans la barre d’application Teams et en recherchant Insights.
- Application personnelle : les chefs d’établissement peuvent ajouter l’application Insights en tant qu’application personnelle (elle s’affiche dans le menu Teams à gauche) en accédant aux Applications dans la barre d’application Teams et en recherchant Insights.

## <a name="compliance"></a>Conformité

Insights a des engagements de conformité de premier plan, et est considéré comme un service de niveau C de l'infrastructure de conformité d’Office 365.

> [!NOTE]
> Visitez le [Centre de gestion de la confidentialité de Microsoft](https://www.microsoft.com/trust-center) pour en savoir plus sur la protection de vos données par Microsoft.

## <a name="privacy"></a>Confidentialité

Les informations collectées et présentées via Insights répondent à plus de 90 normes réglementaires et sectorielles, y compris la loi FERPA (Family Educational Rights and Privacy Act) pour la sécurité des étudiants et des enfants, ainsi que d’autres réglementations axées sur la confidentialité. Il est important que les ITAdmins sachent que les informations collectées par étudiant sont destinées à être utilisées uniquement dans un contexte de cours, afin de permettre aux enseignants et aux chefs d’établissement de déterminer le comportement de la classe. Les informations sont collectées pour des activités d'apprentissage utiles, telles que la participation aux réunions de classe, la publication de messages, la réponse aux billets des camarades de classe, le travail sur des devoirs, l'édition de fichiers, etc. Par exemple, nous n’avons pas d’informations sur la conversation privée ou la connexion Teams.

Notre objectif est d’aider les enseignants à comprendre l’implication et à mettre en valeur l’apprentissage des étudiants. Bien que ces activités de cours puissent se concentrer sur des actions au niveau de l'élève, aucune valeur positive ou négative n'est attribuée à ces actions par Microsoft Teams, et il n'y a pas de jugement d'identification d'étudiants individuels basé sur des critères. Les informations contenues dans Insights informent un enseignant que, par exemple, un étudiant n'a pas été actif dans l'outil à une certaine période ou a terminé tous ses devoirs de la semaine dernière dans les délais. Il incombe à l'enseignant d'interagir avec l'étudiant et sa famille ou ses tuteurs pour déterminer la raison sous-jacente de toute activité ou inactivité détectée.

## <a name="data-collection"></a>Collecte de données

Nous collectons des données pour Class lorsque l'outil Education Analytics est activé pour le client. Les données sont collectées à partir de l’activité Teams afin d’obtenir des informations exploitables pour l’enseignement et l’apprentissage.

Par défaut, Education Analytics est **Activée**.

Pour l’instant, ces données sont extraites des domaines suivants de l’activité des étudiants et des enseignants dans les équipes de classe :

|Composant Teams  |Données collectées  |
|-----------------|------------------------|------------------------|
|Affectations |Ouverture, remise et notation des devoirs. |
|Implication sur les canaux |Visiter un canal, créer un billet, répondre à un billet et l'apprécier (à l'exclusion du contenu de conversation). |
|Fichiers |Charger, télécharger, accéder, modifier, commenter et partager un fichier (à l'exclusion du contenu du fichier). |
|Réunions |Présence (à l'exclusion du contenu des réunions). |

## <a name="data-location"></a>Emplacement des données

Les données Insights pour les locataires résidant en Europe sont stockées sur des serveurs en Europe. Les données relatives aux locataires résidant aux États-Unis sont stockées sur des serveurs aux États-Unis. Si vous utilisez Insights et que votre locataire Office 365 se trouve dans une région en dehors de l'Europe ou des États-Unis, vos données seront stockées dans la région géographique appropriée.

## <a name="performance-and-reliability"></a>Performances et fiabilité

Insights est conçue pour gérer un grand volume de données collectées dans le cadre de l'activité Teams avec des performances et une fiabilité optimales.

Le processus de collecte des données se déroule sur des serveurs distincts, indépendamment de l'installation de l'onglet Insights dans Teams. L'onglet Insights ou l’application personnelle n'affecte pas les performances des applications ni la bande passante du réseau pour les enseignants et les étudiants qui utilisent les autres fonctionnalités de Teams.

> [!TIP]
> Consultez [ici](edu-remote-low-bandwidth.md) la section consacrée à l'utilisation Teams pour l'éducation lorsque la bande passante est faible.

## <a name="how-to-delete-your-data"></a>Comment supprimer vos données

Les services éducatifs enregistrent les actions des étudiants et des enseignants effectuées dans le cadre d'une équipe de classe. Ces données sont considérées comme un ensemble de données mélangées et ne sont donc pas automatiquement supprimées du service une fois que les comptes d'utilisateur des étudiants ou des enseignants sont supprimés de votre organisation.

> [!NOTE]
> La suppression de données a un impact négatif sur la capacité d'Insights à analyser l'implication des équipes de classe au fil du temps.

- Ouvrez un ticket de support [ici](https://edusupport.microsoft.com/support). Le ticket de support doit indiquer clairement la demande d'une opération RGPD Supprimer DSR et contenir l'ID de l'objet utilisateur à supprimer. Il n'est pas possible de limiter l'ensemble des données ou la fenêtre temporelle de la suppression.
- Une fois rempli, le ticket de support attend dans la file d'attente pendant une semaine afin de respecter la stratégie de rétention minimale. Vous avez la possibilité d'annuler l'opération pendant cette période.
- Après une semaine, l’équipe Education Analytics prend des mesures pour s’assurer que toutes les données associées à l’ID utilisateur sont supprimées du service. Le support de Microsoft surveille le ticket ICM et vous informe une fois le processus de suppression terminé, dans un délai maximum de 28 jours.

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a>Désactiver et activer Insights en utilisant School Data Sync (SDS)

School Data Sync(SDS) permet d’automatiser le processus d’importation et de synchronisation des données du SIS avec Office 365.

L’utilisation d’Insights ne nécessite pas l’utilisation de School Data Sync (SDS). Toutefois, vous pouvez choisir de résilier Education Analytics à tout moment en désactivant le bouton bascule dans le Centre d’administration SDS sous **Paramètres** > **Gérer Education Analytics**.

:::image type="content" source="media/class-insights-on-off.png" alt-text="Le commutateur marche/arrêt pour activer ou désactiver Insights.":::

Par défaut, Education Analytics et, par conséquent, Insights, est activée. Lorsque vous choisissez de ne pas participer à Analytics, nous supprimons toutes les données collectées pour l'onglet Insights. Si vous réactivez la fonctionnalité Analytics, nous commençons à collecter des données à partir du moment où elle est réactivée.

En savoir plus : [insights pour les enseignants](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc)
