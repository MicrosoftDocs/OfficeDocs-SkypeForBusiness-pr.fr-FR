---
title: Résoudre les problèmes liés à Career Coach pour Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: a5ebda4324f7cc46d69b882a53684b21b4fa2932
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024147"
---
# <a name="troubleshoot-career-coach-for-microsoft-teams"></a>Résoudre les problèmes liés à Career Coach pour Microsoft Teams

Cet article s’adresse aux administrateurs informatiques de l’enseignement supérieur qui doivent résoudre les problèmes liés à Career Coach pour Microsoft Teams.

Vous trouverez ci-dessous les problèmes courants et les étapes de résolution que les administrateurs informatiques peuvent prendre avec Career Coach.

## <a name="missing-required-configuration-data"></a>Données de configuration requises manquantes

Si vous voyez « Career Coach est en cours de configuration pour que vous l’utilisiez bientôt » dans l’expérience Coach de carrière, **toutes les données de configuration requises n’ont pas été ajoutées**.

Les **sections suivantes doivent être complétées** avant que Career Coach puisse être utilisé :

- [Marque et préférences](career-coach-set-up-steps.md#brand-and-preferences)
- [Connexion LinkedIn](career-coach-set-up-steps.md#linkedin-connection)
- [Catalogue de cours](career-coach-set-up-steps.md#course-catalog)
- [Champs d’étude](career-coach-set-up-steps.md#fields-of-study)

Référencez [l’état de configuration de Career Coach](career-coach-set-up-steps.md#configuration-status) pour voir quels paramètres doivent être complétés.

## <a name="incorrect-formatting-of-course-catalog-or-fields-of-study-data"></a>Mise en forme incorrecte du catalogue course ou des champs de données d’étude

Les CSV pour le catalogue de cours et le champ d’étude ont des formats requis et une taille maximale de 18 Mo.

Référencez le [schéma de document du catalogue de cours](career-coach-set-up-steps.md#course-catalog-document-format-and-schema) Career Coach et les champs Career Coach [du schéma du document d’étude](career-coach-set-up-steps.md#fields-of-study-document-format-and-schema) pour garantir une configuration appropriée.

En outre, un fichier catalogue de cours ne doit pas comporter plus de 15 000 lignes pour garantir un traitement réussi.

## <a name="missing-fields-in-career-coach-settings-pages"></a>Champs manquants dans les pages de paramètres de l’entraîneur de carrière

Les pages des paramètres de l’entraîneur de carrière ont des champs obligatoires. Si les champs nécessaires ne sont pas terminés, la page n’est pas envoyée.

Vous ne verrez peut-être pas de message d’avertissement et la page ne sera pas envoyée.

La soumission réussit lorsque vous voyez une bannière verte en haut de la page.

## <a name="setup-policy-changes-arent-complete"></a>Les modifications apportées à la stratégie d’installation ne sont pas terminées

Si Career Coach n’apparaît pas dans Microsoft Teams pour les utilisateurs, les modifications apportées à la stratégie d’installation n’ont peut-être pas encore pris effet. Career Coach ne sera pas installé et épinglé pour les utilisateurs dans Microsoft Teams tant que les modifications apportées à la stratégie d’installation n’entreront pas en vigueur. L’application des modifications de stratégie peut prendre quelques heures.

Toutefois, Career Coach peut être installé directement à partir de l’App Store Microsoft Teams.

- Si les utilisateurs ne parviennent pas à trouver Career Coach dans l’App Store Microsoft Teams, passez en revue les stratégies d’autorisation de votre application et assurez-vous que Career Coach n’est pas une application bloquée.
- Career Coach est une application Microsoft, et il est recommandé d’autoriser les applications Microsoft par des stratégies d’autorisation. En savoir plus sur [la configuration des stratégies d’autorisation](teams-app-permission-policies.md).

## <a name="career-coach-initialization-isnt-complete"></a>L’initialisation de Career Coach n’est pas terminée

Vous pouvez rencontrer l’erreur suivante : « Nous ne pouvons pas récupérer les paramètres de l’application. Réessayez. Si vous continuez à avoir des problèmes, contactez le support technique Microsoft. »

Vérifiez **l’état de Service Provisioning** dans la [page paramètres de Career Coach](career-coach-set-up-steps.md#career-coach-settings-status).

Si votre locataire est toujours initialisé, patientez 15 minutes, puis réessayez. Ouvrez un ticket de support si vous recevez toujours l’erreur.
