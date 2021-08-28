---
title: Inscrire un appareil salles Teams au service géré Salles Microsoft Teams Premium service
author: v-smandalika
ms.author: v-smandalika
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment inscrire des Salles Microsoft Teams dans Salles Microsoft Teams Premium service géré.
f1keywords: ''
ms.openlocfilehash: a6aa59a798e06c407c1bbde6734ec9ab3ecedcd1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58637019"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Inscrire un appareil dans le service géré Salles Microsoft Teams Premium’équipe

Pour inscrire un appareil Salles Microsoft Teams au service géré par salles Teams Premium, vous devez affecter un utilisateur à l’administrateur de services gérés, puis effectuer les étapes d’inscription à l’aide de cet utilisateur.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Attribuer des utilisateurs au rôle Administrateur de services gérés

Pour attribuer aux utilisateurs le rôle Administrateur de service géré, vous pouvez effectuer les étapes suivantes :

1. Connectez-vous [au salles Teams Premium d’administration](https://portal.rooms.microsoft.com/) avec les mêmes privilèges d’administrateur que celui utilisé pour se connecter à la Centre d’administration Microsoft 365.
2. Accédez à **Paramètres**  >    >  **Paramètres,** puis sélectionnez **Administrateur de services gérés.**
3. Sous **Administrateur de services gérés,** sélectionnez **l’onglet Devoirs,** puis **sélectionnez Ajouter.**
4. Suivez l’Assistant pour nommer l’affectation et sélectionnez les utilisateurs qui doivent y être ajoutés. L’affectation s’applique à tous les groupes de salles et de salles.
5. À la fin de l’Assistant Affectation, **sélectionnez Ajouter un devoir.**

Les utilisateurs à qui est attribué le rôle Administrateur de services gérés sont responsables de la gestion et de la surveillance quotidienne du portail salles Teams Premium service géré.

Après avoir affecté des utilisateurs au rôle Administrateur de service géré, continuez à la [section](#enroll-a-teams-rooms-device) Inscrire un appareil pour ajouter un appareil salles Teams au portail de service géré.

## <a name="enroll-a-teams-rooms-device"></a>Inscrire un salles Teams appareil

Pour inscrire un appareil au service géré, vous salles Teams Premium les étapes suivantes :

1. Connectez-vous [salles Teams Premium au](https://portal.rooms.microsoft.com/) portail d’administration avec un utilisateur à qui le rôle Administrateur de service géré a été attribué.
2. Sélectionnez l’une des sélections **?** dans le coin supérieur droit du portail pour lancer le menu d’aide. Le menu d’aide inclut un [guide d’installation](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) contenant des instructions d’inscription détaillées :

    1. Examinez la section **Conditions préalables** du guide d’installation. Confirmez que les URL répertoriées dans les **URL requises** pour la liste des communications sont ajoutées à la liste d’adresses autoriser du trafic de votre pare-feu.
    2. Suivez les instructions de la section Activation de **la Paramètres TPM** pour activer la fonctionnalité module de plateforme fiable (TPM) sur votre appareil.
    3. Suivez les instructions de la section **Ajout** de Paramètres proxy pour configurer votre appareil de manière à utiliser votre passerelle proxy, si vous en avez une.
    4. Suivez les instructions de la section **Processus** pour installer le logiciel de l’agent de surveillance et configurer la clé d’inscription automatique sur votre appareil.

3. Une fois l’agent de surveillance et la clé XML unique configurées sur votre appareil, accédez à Salles **>** nom de la salle > **statut,** puis sélectionnez **Inscrire.**

    > [!NOTE]
    > Le salles Teams reste dans l’état Intégration jusqu’à ce qu’un administrateur de service géré inscrit l’appareil à l’aide du portail. 

## <a name="link-to-installation-guide"></a>Lien vers le guide d’installation

Le  menu Aide fournit un lien vers le guide [d’installation](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) qui fournit à son tour les informations suivantes :

- Instructions sur les URL qui doivent être activées pour que la télémétrie de salle soit envoyée au service géré.
- Instructions pour l’application de l Salles Microsoft Teams Premium de surveillance et de la clé XML unique dans le cadre de l’inscription d’un appareil au service géré.
- Instructions de dépannage.
