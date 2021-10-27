---
title: Panneau de contrôle - Vue d’ensemble
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/13/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: Cet article fournit une vue d’ensemble du nouveau Panneau de contrôle.
ms.openlocfilehash: 8a4f8e073b424969951a69c620dd5f65a582fd75
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579871"
---
# <a name="control-panel"></a>Panneau de contrôle

Le Panneau de contrôle actuel est une nouvelle version du Panneau de contrôle hérité, avec laquelle il existe en tandem. Le nouveau Panneau de contrôle a été mis en place à partir de la mise à jour cumulative de juillet 2019. Il permet de gérer la configuration des serveurs, des utilisateurs, des clients et des appareils dans l’environnement d’une organisation.

Le panneau de contrôle hérité peut ne pas fonctionner, car la technologie Silverlight a atteint l’étape « fin de la prise en charge » le 12 octobre 2021. Pour plus d’informations, voir [Fin du support de Silverlight.](https://support.microsoft.com/windows/silverlight-end-of-support-0a3be3c7-bead-e203-2dfd-74f0a64f1788)

> [!NOTE]
> Pour plus d’informations sur le Panneau de contrôle hérité, voir [Panneau](../SfbServer/management-tools/install-and-open-administrative-tools.md)de **Skype Entreprise Server.**

## <a name="access-control-panel"></a>Panneau de contrôle d’accès

Pour lancer le nouveau Panneau de configuration dans le navigateur, entrez https:// &lt; pool-FQDN /macp ou une &gt; URL simple configurée.

Le nouveau Panneau de contrôle inclut des éléments de menu couramment utilisés qui couvrent la plupart des besoins de l’organisation. Il existe quelques éléments de menu du Panneau de contrôle hérité qui ne sont pas disponibles dans le nouveau Panneau de contrôle. Toutefois, l’utilisateur peut utiliser les fonctionnalités de ces éléments de menu via les cmdlets PowerShell. Pour plus d’informations, voir le tableau ci-dessous.

> [!NOTE]
> La documentation relative aux autres éléments de menus sera disponible par la suite de manière progressive.

## <a name="client"></a>Client

|Sous-menu  |Source d’informations pour la cmdlet  |
|---------|---------|
|Stratégie de version du client         |    [Stratégie de version du client](use-powershell-client-menu.md#client-version-policy)     |
|Configuration de version du client      |  [Configuration de version du client](use-powershell-client-menu.md#client-version-configuration)       |
|Mise à jour de l’appareil    | [Mise à jour du périphérique](use-powershell-client-menu.md#device-update)        |
|Test d’appareil     | [Périphérique de test](use-powershell-client-menu.md#test-device)        |
|Configuration du fichier journal de l’appareil         |    [Configuration du fichier journal du périphérique](use-powershell-client-menu.md#device-log-configuration)     |
|Configuration de l’appareil         |    [Configuration des périphériques](use-powershell-client-menu.md#device-configuration)     |
|Stratégie de mobilité         |    [Stratégie de mobilité](use-powershell-client-menu.md#mobility-policy)     |
|Configuration des notifications Push         |    [Configuration des notifications Push](use-powershell-client-menu.md#push-notification-configuration)     |