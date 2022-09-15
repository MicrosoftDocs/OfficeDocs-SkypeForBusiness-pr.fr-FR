---
title: Stratégies de numéros gratuits d’audioconférence
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: mshaikh
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.overview
description: Découvrez comment l’audioconférence dans Microsoft 365 ou Office 365 permet aux utilisateurs d’appeler des réunions à partir de leur téléphone.
ms.openlocfilehash: 8fcc731f208dc3fecd42dd2c351714f67ad6a684
ms.sourcegitcommit: 44d9f15f7f7c00b3651a11ff1e8b37dda1716a52
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67732403"
---
# <a name="audio-conferencing-policy-settings-for-toll-and-toll-free-numbers"></a>Paramètres de stratégie d’audioconférence pour les numéros payants et gratuits

## <a name="teams-audio-conferencing-policy"></a>Stratégie d’audioconférence Teams

Utilisez des stratégies d’audioconférence pour gérer les numéros payants et gratuits d’audioconférence à afficher dans les invitations aux réunions créées par les utilisateurs au sein de votre organisation. Vous pouvez utiliser l’une des deux stratégies créées automatiquement ou créer et affecter des stratégies personnalisées. Les deux stratégies créées automatiquement sont globales (par défaut à l’échelle de l’organisation) et AllowTollFreeDialinFalse (affectées à tous les utilisateurs existants au sein de l’organisation qui ne sont pas activés pour les numéros de numérotation gratuits). Vous gérez les stratégies d’audioconférence dans le Centre d’administration Microsoft Teams ou à l’aide de [PowerShell](teams-powershell-overview.md).

- Le paramètre AllowTollFreeDialin ne peut plus être géré pour un utilisateur individuel via le Centre d’administration Teams ou PowerShell. Les administrateurs de locataires pourront uniquement gérer ce paramètre via la nouvelle stratégie d’audioconférence.
- La stratégie globale ne peut pas être modifiée à partir du Centre d’administration Teams.

> [!NOTE]
> Les stratégies d’audioconférence personnalisées ne sont pas prises en charge pour les clients activés pour Skype Entreprise réunions hébergées en région. Les clients activés pour les réunions hébergées au niveau régional peuvent gérer les paramètres d’audioconférence des utilisateurs via leurs paramètres par défaut. Les paramètres par défaut de l’audioconférence des utilisateurs peuvent être modifiés dans le Centre de Administration Teams en accédant à **Users** -> **Manage Users** -> **Select User** -> **Account**.

Lorsqu’une stratégie d’audioconférence Teams est activée dans le locataire, deux stratégies créées automatiquement sont disponibles dans le locataire. Les deux stratégies créées automatiquement et leurs paramètres par défaut sont les suivants :

### <a name="global-org-wide-default"></a>Global (par défaut à l’échelle de l’organisation)

Dans cette stratégie, la valeur de **AllowTollfreedialin** est activée et aucun numéro de téléphone n’est défini dans la stratégie. Il s’agit de la stratégie par défaut pour tous les utilisateurs du locataire qui, au moment du lancement, ont **défini AllowTollfreedialin** **sur Activé**.
Étant donné que la stratégie n’a pas de numéros de téléphone définis, lorsque les utilisateurs de cette stratégie créent une réunion Teams, les numéros de téléphone disponibles dans leur réunion sont les mêmes que ceux que les utilisateurs avaient avant la stratégie. Ces numéros de téléphone sont normalement par défaut le pays/l’emplacement de l’utilisateur, sauf modification par l’administrateur du locataire pour les utilisateurs individuels.

Par exemple, si un utilisateur basé hors d’Allemagne a reçu un numéro de téléphone gratuit et payant en Allemagne avant le lancement de la stratégie d’audioconférence, au lancement, l’utilisateur se voit attribuer la stratégie globale et les numéros de téléphone qu’il continuera de voir dans son invitation à la réunion seront les mêmes qu’avant l’application de la stratégie (autrement dit,  les numéros payants et gratuits allemands). Un utilisateur final ne voit aucune modification lors du lancement de la stratégie. Toutefois, si un administrateur de locataire modifie la stratégie globale et inclut des numéros de téléphone spécifiques dans la stratégie qui sont différents de ceux d’avant, tous les utilisateurs de la stratégie voient uniquement les numéros de téléphone inclus dans la stratégie dans les réunions qu’ils planifient.

> [!NOTE]
> Si, au lieu de modifier la stratégie globale, un administrateur de locataire crée une stratégie personnalisée et l’applique aux utilisateurs, les paramètres définis dans la stratégie personnalisée sont ceux que les utilisateurs finaux voient dans leur invitation à la réunion.

Par exemple, si la stratégie personnalisée a « AllowTollFreeDialinFalse » et qu’aucun numéro de téléphone n’est défini, les utilisateurs de cette stratégie ne pourront pas avoir de numéros gratuits et, dans la mesure où aucun numéro de téléphone n’est défini dans la stratégie, le numéro de téléphone payant qui sera utilisé dans les invitations à la réunion créées par ces utilisateurs sera le même que celui que les utilisateurs avaient avant la stratégie. Ces numéros de téléphone sont normalement par défaut le pays/l’emplacement de l’utilisateur, sauf modification par l’administrateur du locataire pour les utilisateurs individuels.

### <a name="allowtollfreedialinfalse"></a>AllowTollfreedialinFalse

Dans cette stratégie, la valeur de **AllowTollfreedialin** est **désactivée** et aucun numéro de téléphone n’est défini dans la stratégie. Il s’agit de la stratégie par défaut pour tous les utilisateurs du locataire qui, au moment du lancement, ont **défini AllowTollfreedialin** sur **Désactivé**.

Étant donné que la stratégie n’a pas de numéros de téléphone définis, lorsque les utilisateurs de cette stratégie créent une réunion d’équipe, les numéros de téléphone qui seront disponibles dans leur réunion sont les mêmes que ceux que les utilisateurs avaient avant la stratégie. Ces numéros de téléphone sont normalement par défaut le pays, la région ou l’emplacement de l’utilisateur, sauf si cela a été modifié par l’administrateur du locataire pour les utilisateurs individuels.

Par exemple, si un utilisateur basé en Allemagne a un numéro de téléphone payant allemand attribué avant le lancement d’une stratégie d’audioconférence, au lancement, l’utilisateur se voit attribuer la stratégie « AllowTollfreedialinFalse » et les numéros de téléphone qu’il continuera à voir dans son invitation à la réunion seront les mêmes qu’auparavant (autrement dit, le numéro de téléphone allemand). Un utilisateur final ne voit aucune modification lors du lancement de la stratégie. Toutefois, si un administrateur de locataire modifie la stratégie **AllowTollfreedialinFalse** et inclut des numéros de téléphone spécifiques dans la stratégie, tous les utilisateurs de la stratégie voient uniquement les numéros de téléphone inclus dans la stratégie dans les réunions qu’ils planifient.

## <a name="create-a-custom-audio-conferencing-policy"></a>Créer une stratégie d’audioconférence personnalisée

Vue d’ensemble des étapes :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à Réunions > Audioconférence.
1. Sélectionnez Ajouter.
1. Entrez le nom et la description de la stratégie. Le nom ne peut pas contenir de caractères spéciaux et ne doit pas dépasser 64 caractères.
1. Sélectionnez les paramètres de votre choix.
1. Sélectionnez Enregistrer.

Par exemple, vous pouvez avoir un groupe d’utilisateurs qui ont régulièrement des réunions avec des participants de plusieurs pays. Dans notre exemple, les participants viennent du Canada, du Botswana et de Singapour et ils veulent tous participer à la réunion par audioconférence en numérotant un numéro de téléphone. Vous pouvez créer une stratégie personnalisée nommée « Canada Botswana Singapour » et sélectionner les numéros de téléphone de ces trois pays à inclure dans la stratégie par le biais de l’option **Ajouter un numéro de téléphone** , puis enregistrer cette stratégie. Vous pouvez ensuite affecter cette stratégie aux utilisateurs requis.

Cela garantit que les numéros de téléphone que vous avez sélectionnés pour le Canada, le Botswana et Singapour seront inclus dans les invitations aux réunions créées par les utilisateurs de cette politique.

### <a name="step-by-step-instructions-on-creating-a-custom-policy-based-on-the-example"></a>Instructions pas à pas sur la création d’une stratégie personnalisée basée sur l’exemple

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **l’audioconférence** **Réunions** > .
2. Sélectionnez **Ajouter**.
3. Entrez le nom et la description de la stratégie. Le nom ne peut pas contenir de caractères spéciaux et ne doit pas dépasser 64 caractères.
4. Choisissez d’inclure ou non des numéros gratuits dans les réunions créées par les utilisateurs de cette stratégie. La définition de cette option **sur Activé** vous permet d’ajouter des numéros de téléphone gratuits dans cette stratégie.
5. Sélectionnez Ajouter un numéro de téléphone.
6. Un volet s’ouvre à droite de l’écran, contenant la zone **Rechercher par emplacement** .
7. Entrez le Canada, puis sélectionnez un numéro de téléphone à partir du Canada dans les résultats.
8. Sélectionnez **Ajouter**.
9. Répétez les étapes 6 et 7 de la même façon pour rechercher et ajouter des numéros de téléphone à partir du Botswana et de Singapour.
10. Sélectionnez des numéros gratuits si vous avez activé le paramètre **pour inclure des numéros gratuits dans les réunions créées par les utilisateurs de cette stratégie** à l’étape 4.
11. Sélectionnez **Ajouter** dans le coin inférieur droit du volet. Les numéros de téléphone des trois pays que vous avez sélectionnés sont répertoriés.
12. Il existe une colonne de classement qui détermine l’ordre dans lequel les numéros de téléphone seront affichés dans les invitations aux réunions créées par les utilisateurs de cette stratégie. Vous pouvez modifier l’ordre en sélectionnant un numéro de téléphone et en le déplaçant vers le haut ou vers le bas à l’aide des boutons **Monter** et **Descendre** , respectivement.
13. Une fois que vous avez placé les numéros de téléphone dans l’ordre de votre préférence, **sélectionnez Enregistrer**.
14. Votre stratégie personnalisée nommée « Canada Botswana Singapour » est créée.
15. Une fois la création terminée, vous pouvez affecter cette stratégie à vos utilisateurs.

## <a name="edit-a-meeting-policy"></a>Modifier une stratégie de réunion

Vous pouvez modifier toutes les stratégies personnalisées que vous créez. (Notez que la stratégie globale ne peut pas être modifiée à partir du Centre d’administration Teams)

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **l’audioconférence** **Réunions** > .
1. Choisissez la stratégie à modifier en sélectionnant à gauche du nom de la stratégie, puis en sélectionnant **Modifier**.
1. Apportez des modifications.
1. Sélectionnez **Enregistrer**.

> [!NOTE]
> Vous ne pouvez pas supprimer une stratégie qui est attribuée à des utilisateurs. Vous devrez affecter une stratégie différente à tous les utilisateurs affectés, puis vous pourrez supprimer la stratégie d’origine.

## <a name="assign-a-meeting-policy-to-users"></a>Affecter une stratégie de réunion aux utilisateurs

> [!IMPORTANT]
> Une fois qu’une nouvelle stratégie d’audioconférence est appliquée à un utilisateur, les numéros de téléphone définis dans la stratégie ne sont disponibles que dans les nouvelles réunions créées par l’utilisateur avec cette stratégie. Toutes les réunions anciennes et périodiques planifiées avant la stratégie continueront d’afficher les anciens paramètres, par exemple un numéro payant et un numéro gratuit (si le numéro gratuit a été activé pour cet utilisateur). Un scénario ici pourrait être qu’un utilisateur ait activé **l’option Autoriser le numéro** gratuit et qu’un numéro gratuit ait été attribué, et qu’il ait créé des réunions périodiques pour l’avenir. Dans ce scénario, si vous créez une stratégie personnalisée avec AllowTollfreeDialIn **désactivé et** l’appliquez à cet utilisateur, les nouvelles réunions créées par cet utilisateur n’incluent pas de numéros gratuits, mais les réunions anciennes et périodiques affichent toujours des numéros gratuits. Par conséquent, si les appelants composent ce numéro gratuit pour participer à la réunion, l’appel échoue, car le numéro gratuit est désormais désactivé pour cet utilisateur en raison de la stratégie. Pour éviter cela, vous pouvez migrer les anciennes réunions des utilisateurs après leur avoir attribué la nouvelle stratégie d’audioconférence. Veuillez consulter [l’utilisation du service de migration de réunion (MMS).](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

Vous pouvez affecter une stratégie directement aux utilisateurs ou à un groupe dont les utilisateurs sont membres (s’ils sont pris en charge pour le type de stratégie), individuellement ou en plus grand nombre via une affectation par lots (si elle est prise en charge pour le type de stratégie).

Pour en savoir plus sur les différentes façons d’affecter des stratégies aux utilisateurs, consultez [Affecter des stratégies aux utilisateurs et aux groupes](assign-policies-users-and-groups.md).

> [!NOTE]
> Un utilisateur ne peut se faire attribuer qu’une seule stratégie d’audioconférence à la fois.

> [!IMPORTANT]
> Jusqu’à 24 heures peuvent être nécessaires pour que les numéros de téléphone attribués s’affichent sur votre invitation à la réunion. Si vous ne voyez pas les numéros mis à jour s’afficher, patientez au moins 24 heures avant de contacter le support technique.

### <a name="known-issue"></a>Problème connu

Lorsque vous démarrez une réunion à l’aide de l’option **Meet now** de Microsoft Teams > Calendar > Meet Mow, si vous sélectionnez ensuite les points de suspension ... option de menu, puis Informations de réunion, il y aura un problème avec la partie inférieure de la section sous **Ou appeler (audio uniquement).** Tous les numéros de téléphone définis dans la stratégie s’affichent, mais l’alignement des numéros rend la lecture difficile.
