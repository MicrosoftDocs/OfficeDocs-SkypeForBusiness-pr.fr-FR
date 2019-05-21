---
title: Supprimer une collection existante de paramètres de configuration de Trunk SIP dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Les paramètres de configuration du Trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté (PSTN), un échange de succursale public (PBX) ou un contrôleur de bordure de session (SBC) au fournisseur de services. '
ms.openlocfilehash: 55636cc34df4b05ccdd4b9035ef3aa4bb169e9a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274932"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Supprimer une collection existante de paramètres de configuration de Trunk SIP dans Skype entreprise Server

Les paramètres de configuration du Trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté (PSTN), un échange de succursale public (PBX) ou un contrôleur de bordure de session (SBC) au fournisseur de services. Ces paramètres spécifient, par exemple :

- si la déviation du trafic multimédia doit être activée sur les jonctions ;
- Les conditions dans lesquelles les paquets de contrôle de transport en temps réel (RTCP) sont envoyés.
- Le chiffrement SRTP (Secure Real-Time Protocol) est requis sur chaque Trunk.

Lorsque vous installez Skype entreprise Server, une collection globale de paramètres de configuration SIP Trunk est créée pour vous. Cette collection globale de paramètres ne peut pas être supprimée. Toutefois, vous pouvez utiliser le panneau de ServerControl Skype entreprise ou l’applet de l’applet de [suppression CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) pour «réinitialiser» les propriétés de la collection globale à leurs valeurs par défaut. Par exemple, si vous avez défini la propriété Enable3pccRefer sur true, lorsque vous réinitialisez la collection globale, la propriété Enable3pccRefer rétablira sa valeur par défaut false.

Les administrateurs peuvent aussi créer des paramètres de configuration de jonction personnalisés étendus à un site ou un service (pour une passerelle RTC individuelle). Ces paramètres personnalisés peuvent être supprimés. Lors de la suppression de ces paramètres personnalisés, tenez compte des points suivants :

- Si vous supprimez des paramètres étendus à un service, la jonction SIP (Session Initiation Protocol) gérée par ces paramètres est gérée par les paramètres appliqués à son site, le cas échéant. En l’absence de paramètres de site, la jonction est gérée par la collection globale de paramètres de configuration de jonction.
- Si vous supprimez des paramètres étendus à un site, les jonctions SIP (Session Initiation Protocol) gérées par ces paramètres sont alors gérées par la collection globale de paramètres de configuration de jonction.

**Pour supprimer les paramètres de configuration de Trunk avec le panneau de configuration Skype entreprise Server** 

1. Dans le panneau de configuration Skype entreprise Server, cliquez sur **routage des communications vocales**, puis cliquez sur Configuration de **Trunk**.
2. Dans l’onglet **configuration de Trunk** , sélectionnez l’ensemble de paramètres de configuration de Trunk SIP à supprimer, cliquez sur **modifier**, puis sur **supprimer**. Pour supprimer plusieurs collections en une seule opération, cliquez sur la première collection à supprimer, maintenez la touche Ctrl enfoncée et cliquez sur les autres collections à supprimer.
3. La propriété **État** de la collection est définie sur la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Tout valider**.
4. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.
5. Dans la boîte de dialogue **panneau de configuration Skype entreprise Server** , cliquez sur **OK**.
6. Si vous changez d’avis et décidez de ne pas supprimer la collection, cliquez sur **valider**, puis cliquez sur **Annuler toutes les modifications non validées**. Lorsque la boîte de dialogue **panneau de configuration Skype entreprise Server** s’affiche, cliquez sur **OK**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Supprimer les paramètres de configuration de ligne à l’aide des cmdlets Windows PowerShell


Vous pouvez supprimer des paramètres de configuration d’une ligne à l’aide de Windows PowerShell et de l’applet de passe **Remove-CsTrunkConfiguration** . Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 

**Pour supprimer une collection de paramètres spécifiée**

La commande ci-dessous supprime les paramètres de configuration de jonction appliqués au site Redmond :

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**Pour supprimer toutes les collections appliquées dans l’étendue du site**

Cette commande supprime tous les paramètres de configuration de jonction appliqués dans l’étendue du site :

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**Pour supprimer toutes les collections pour lesquelles la déviation du trafic multimédia est activée**

La commande ci-dessous supprime tous les paramètres de configuration de jonction pour lesquels la déviation du trafic multimédia est activée :

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) .
