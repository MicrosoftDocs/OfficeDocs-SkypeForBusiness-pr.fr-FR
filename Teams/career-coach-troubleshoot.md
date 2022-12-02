---
title: Résoudre les problèmes de Career Coach pour Microsoft Teams
author: DaniEASmith
ms.author: danismith
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment résoudre les problèmes courants dans Career Coach pour Microsoft Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c00837c40fe405ab4d9d608326a12567843c8bb
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242448"
---
# <a name="troubleshoot-career-coach-for-microsoft-teams"></a>Résoudre les problèmes de Career Coach pour Microsoft Teams

Cet article est destiné aux administrateurs informatiques de l’éducation qui doivent résoudre les problèmes de Career Coach pour Microsoft Teams.

Vous trouverez ci-dessous les problèmes courants et les étapes de résolution que les administrateurs informatiques peuvent suivre avec Career Coach.

## <a name="missing-required-configuration-data"></a>Données de configuration requises manquantes

Si vous voyez « Career Coach est en cours de configuration pour que vous l’utilisiez bientôt » dans l’expérience Career Coach, **toutes les données de configuration requises n’ont pas été ajoutées**.

La [connexion LinkedIn](career-coach-set-up-steps.md#linkedin-connection-required) doit être entièrement configurée pour votre établissement.

Reportez-vous à [l’état de configuration de Career Coach](career-coach-set-up-steps.md#configuration-status) pour voir quels paramètres doivent être renseignés.

## <a name="incorrect-formatting-of-course-catalog-or-fields-of-study-data"></a>Mise en forme incorrecte des données du catalogue de cours ou des champs d’étude

Les CSV pour le catalogue de cours et le domaine d’étude ont des formats requis et une taille maximale de 18 Mo.

Référencez le [schéma de document du catalogue de cours](career-coach-set-up-steps.md#course-catalog-document-format-and-schema) Career Coach et [le schéma du document des champs d’étude](career-coach-set-up-steps.md#fields-of-study-document-format-and-schema) Career Coach pour garantir une configuration appropriée.

En outre, un fichier catalogue de cours ne doit pas comporter plus de 15 000 lignes pour garantir la réussite du traitement.

## <a name="missing-fields-in-career-coach-settings-pages"></a>Champs manquants dans les pages de paramètres Career Coach

Les pages de paramètres Career Coach ont des champs obligatoires. Si les champs nécessaires ne sont pas renseignés, la page ne sera pas envoyée.

Vous ne voyez peut-être pas de message d’avertissement et la page ne sera pas envoyée.

La soumission réussit lorsque vous voyez une bannière verte en haut de la page.

## <a name="setup-policy-changes-arent-complete"></a>Les modifications de la stratégie d’installation ne sont pas terminées

Si Career Coach n’apparaît pas dans Microsoft Teams pour les utilisateurs, les modifications de la stratégie de configuration n’ont peut-être pas encore pris effet. Career Coach ne sera pas installé et épinglé pour les utilisateurs dans Microsoft Teams tant que les modifications de la stratégie d’installation n’entreront pas en vigueur. L’application des modifications de stratégie peut prendre quelques heures.

Toutefois, Career Coach peut être installé directement à partir du magasin d’applications Microsoft Teams.

- Si les utilisateurs ne parviennent pas à trouver Career Coach dans le magasin d’applications Microsoft Teams, passez en revue vos stratégies d’autorisation d’application et vérifiez que Career Coach n’est pas une application bloquée.
- Career Coach est une application Microsoft et il est recommandé d’autoriser Microsoft applications par des stratégies d’autorisation. En savoir plus sur [la configuration des stratégies d’autorisation](teams-app-permission-policies.md).

## <a name="career-coach-initialization-isnt-complete"></a>L’initialisation de Career Coach n’est pas terminée

Vous pouvez rencontrer l’erreur suivante : « Nous ne pouvons pas récupérer les paramètres de l’application. Réessayez. Si vous continuez à avoir des problèmes, contactez Microsoft support client. »

Vérifiez **l’état de l’approvisionnement du service** dans la [page des paramètres Career Coach](career-coach-set-up-steps.md#career-coach-settings-status).

Si votre locataire est toujours en cours d’initialisation, attendez 15 minutes, puis réessayez. Ouvrez un ticket de support si vous recevez toujours l’erreur.
