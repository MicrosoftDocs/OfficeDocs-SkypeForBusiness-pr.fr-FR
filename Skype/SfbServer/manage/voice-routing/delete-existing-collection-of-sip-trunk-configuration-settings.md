---
title: Supprimer une collection existante de paramètres de configuration jonction SIP dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Paramètres de configuration de jonction SIP définissent les relations et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté, un autocommutateur public-IP (PBX) ou un contrôleur de bordure de Session (SBC) au niveau du fournisseur de service. '
ms.openlocfilehash: 6a7c90bf7ff435b0936b34bc57d391e06093040a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879363"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Supprimer une collection existante de paramètres de configuration jonction SIP dans Skype pour Business Server

Paramètres de configuration de jonction SIP définissent les relations et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté, un autocommutateur public-IP (PBX) ou un contrôleur de bordure de Session (SBC) au niveau du fournisseur de service. Ces paramètres spécifient, par exemple :

- si la déviation du trafic multimédia doit être activée sur les jonctions ;
- Les conditions dans lesquelles les paquets Real-Time transport control protocol (RTCP) sont envoyés.
- Ou non sécurisé en temps réel (chiffrement SRTP protocol) est requis sur chaque jonction.

Lorsque vous installez Skype pour Business Server, une collection de paramètres de configuration de jonction SIP globale est créée pour vous. Cette collection de paramètres globale ne peuvent pas être supprimée. Toutefois, vous pouvez utiliser la Skype pour le panneau de configuration de Business ServerControl ou l’applet de commande [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) « réinitialiser » les propriétés dans la collection globale à leurs valeurs par défaut. Par exemple, si vous avez défini la propriété Enable3pccRefer la valeur True, lorsque vous réinitialisez la collection globale, la propriété Enable3pccRefer est rétabli à sa valeur par défaut False.

Les administrateurs peuvent aussi créer des paramètres de configuration de jonction personnalisés étendus à un site ou un service (pour une passerelle RTC individuelle). Ces paramètres personnalisés peuvent être supprimés. Lors de la suppression de ces paramètres personnalisés, tenez compte des points suivants :

- Si vous supprimez des paramètres étendus à un service, la jonction SIP (Session Initiation Protocol) gérée par ces paramètres est gérée par les paramètres appliqués à son site, le cas échéant. En l’absence de paramètres de site, la jonction est gérée par la collection globale de paramètres de configuration de jonction.
- Si vous supprimez des paramètres étendus à un site, les jonctions SIP (Session Initiation Protocol) gérées par ces paramètres sont alors gérées par la collection globale de paramètres de configuration de jonction.

**Pour supprimer les paramètres de configuration de jonction avec le Skype pour Business Server Control Panel** 

1. Dans Skype pour Business Server le panneau de configuration, cliquez sur **Routage des communications vocales**, puis cliquez sur **Configuration de jonction**.
2. Sous l’onglet **Configuration de jonction** , sélectionnez la collection de paramètres de configuration de jonction SIP à supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**. Pour supprimer plusieurs collections en une seule opération, cliquez sur la première collection à supprimer, maintenez la touche Ctrl enfoncée et cliquez sur les autres collections à supprimer.
3. La propriété **État** de la collection est définie sur la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Tout valider**.
4. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.
5. Dans la boîte de dialogue **Skype pour Business Server le panneau de configuration** , cliquez sur **OK**.
6. Si vous changez d’avis et que vous décidez de ne pas supprimer de la collection, cliquez sur **Valider**, puis cliquez sur **Annuler toutes les modifications non validées**. Lorsque la boîte de dialogue **Skype pour le panneau de configuration serveur Business** s’affiche, cliquez sur **OK**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration de jonction à l’aide des applets de commande Windows PowerShell


Vous pouvez supprimer les paramètres de configuration de jonction à l’aide de Windows PowerShell et l’applet de commande **Remove-CsTrunkConfiguration** . Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. 

**Pour supprimer une collection de paramètres spécifiée**

La commande ci-dessous supprime les paramètres de configuration de jonction appliqués au site Redmond :

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**Pour supprimer toutes les collections appliquées dans l’étendue du site**

Cette commande supprime tous les paramètres de configuration de jonction appliqués dans l’étendue du site :

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**Pour supprimer toutes les collections pour lesquelles la déviation du trafic multimédia est activée**

La commande ci-dessous supprime tous les paramètres de configuration de jonction pour lesquels la déviation du trafic multimédia est activée :

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) .
