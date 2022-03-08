---
title: Inscrire un appareil salles Teams au service géré Salles Microsoft Teams Premium’équipe
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
description: Découvrez comment inscrire des comptes Salles Microsoft Teams service géré Salles Microsoft Teams Premium service.
f1keywords: ''
ms.openlocfilehash: d00c4f84447e8ba41f0328cca9b907db45e8fdb7
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070413"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Inscrire un appareil dans le service géré Salles Microsoft Teams Premium’équipe

Pour inscrire un appareil Salles Microsoft Teams au service géré par salles Teams Premium, vous devez affecter un ou plusieurs utilisateurs à l’administrateur de service géré, puis effectuer les étapes d’inscription à l’aide de cet utilisateur.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Attribuer des utilisateurs au rôle Administrateur de services gérés

Pour attribuer aux utilisateurs le rôle Administrateur de service géré, vous pouvez effectuer les étapes suivantes :

1. Connectez-vous [au salles Teams Premium d’administration](https://portal.rooms.microsoft.com/) avec les mêmes privilèges d’administrateur que celui utilisé pour se connecter à la Centre d'administration Microsoft 365.
2. Accédez à **Paramètres** >  **Paramètres** >  **Puis** sélectionnez **Administrateur de services gérés**.
3. Sous **Administrateur de services gérés**, sélectionnez **l’onglet Devoirs** , puis **Sélectionnez Ajouter**.
4. Suivez l’Assistant pour nommer l’affectation et sélectionnez les utilisateurs qui doivent y être ajoutés. L’affectation s’applique à tous les groupes de salles et de salles.
5. À la fin de l’Assistant Affectation, **sélectionnez Ajouter un devoir**.

Les utilisateurs à qui est attribué le rôle Administrateur de services gérés sont responsables de la gestion et de la surveillance au quotidien du portail salles Teams Premium service géré.

Après avoir affecté des utilisateurs au rôle Administrateur de service géré, continuez à inscrire un appareil [salles Teams](enroll-a-device.md) pour ajouter un appareil salles Teams au portail de service géré.

<!-- ## Enroll a Teams Rooms device

 To enroll a device in the Teams Rooms Premium managed service, see [Monitoring device software installation](monitor-software-installation-guide.md).

2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

    1. Review the **Pre-requisites** section in the Installation guide. Confirm that the URLs listed in the **URLs Required for Communication** list are added to your firewall's traffic allow list.
    2. Follow the instructions in the **Enabling TPM Settings** section to enable the Trusted Platform Module (TPM) functionality on your device.
    3. Follow the instructions in the **Adding Proxy Settings** section to configure your device to use your proxy gateway, if you have one.
    4. Follow the instructions in the **Process** section to install the monitoring agent software and configure the self enrollment key on your device.

3. After the monitoring agent and unique XML key are configured on your device, navigate to **Rooms** > room name > **Status**, and then select **Enroll**.

    > [!NOTE]
    > The Teams Rooms device will remain in the **Onboarding** state until a Managed Service Administrator enrolls the device using the portal.

    See [Monitoring device software installation](monitoring-software-installation-guide.md).

<!--## Link to Installation guide

The **Help** menu provides a link to the [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) which in turn provides the following information:

- Instructions on URLs that need to be allow-listed to serve to enable room telemetry to be sent to the managed service.
- Instructions for applying the Microsoft Teams Rooms Premium monitoring agent and unique XML key as part of enrolling a device in the managed service.
- Troubleshooting instructions.-->
