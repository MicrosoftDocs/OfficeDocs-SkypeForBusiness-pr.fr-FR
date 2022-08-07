---
title: Inscrire un appareil salles Teams dans le service managé Salles Microsoft Teams Premium
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment inscrire des comptes Salles Microsoft Teams dans Salles Microsoft Teams Premium service managé.
f1keywords: ''
ms.openlocfilehash: f721406381e1eb99584563473196893bc21cf39b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270999"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Inscrire un appareil dans le service managé Salles Microsoft Teams Premium

Pour inscrire un appareil Salles Microsoft Teams dans le service managé Salles Teams Premium, vous devez affecter un ou plusieurs utilisateurs à l’administrateur du service géré, puis effectuer les étapes d’inscription à l’aide de cet utilisateur.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Affecter des utilisateurs au rôle Administrateur de service géré

Effectuez les étapes suivantes pour affecter des utilisateurs au rôle Administrateur du service géré :

1. Connectez-vous au [portail salles Teams Premium](https://portal.rooms.microsoft.com/) avec les mêmes privilèges d’administrateur que ceux utilisés pour vous connecter au Centre d'administration Microsoft 365.
2. Accédez aux **rôles** **paramètres** >  > , puis sélectionnez **Administrateur de service géré**.
3. Sous **Administrateur du service géré**, sélectionnez l’onglet **Affectations** , puis **Ajouter**.
4. Suivez l’Assistant pour nommer l’affectation et sélectionnez les utilisateurs qui doivent y être ajoutés. L’affectation s’appliquera à toutes les salles et groupes de salles.
5. À la fin de l’Assistant Affectation, **sélectionnez Ajouter une affectation**.

Les utilisateurs auxquels le rôle Administrateur de service administré est attribué sont responsables de la gestion et de la surveillance quotidiennes du portail de service managé salles Teams Premium.

Une fois que vous avez affecté des utilisateurs au rôle Administrateur du service géré, passez à [l’inscription d’un appareil salles Teams](enroll-a-device.md) pour ajouter un appareil salles Teams au portail de service managé.

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
