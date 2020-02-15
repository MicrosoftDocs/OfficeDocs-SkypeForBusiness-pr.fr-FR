---
title: Suppression d’une collection existante de paramètres de configuration de jonction SIP dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. '
ms.openlocfilehash: 09f5e7fda03c5e0e5221661f87482b67192ce302
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045056"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Suppression d’une collection existante de paramètres de configuration de jonction SIP dans Skype entreprise Server

Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :

- L’activation ou non du contournement de média sur les jonctions.
- Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).
- L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.

Lorsque vous installez Skype entreprise Server, une collection globale de paramètres de configuration de jonction SIP est créée pour vous. Cette collection globale de paramètres ne peut pas être supprimée. Toutefois, vous pouvez utiliser le panneau ServerControl de Skype entreprise ou l’applet de commande [Remove-applet cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) pour réinitialiser les propriétés de la collection globale à leurs valeurs par défaut. Par exemple, si vous avez défini la propriété Enable3pccRefer sur true, lorsque vous réinitialisez la collection globale, la propriété Enable3pccRefer reprend sa valeur par défaut false.

Les administrateurs peuvent aussi créer des paramètres de configuration de jonction personnalisés étendus à un site ou un service (pour une passerelle PSTN individuelle) ; ces paramètres personnalisés peuvent être supprimés. Au moment de supprimer ces paramètres personnalisés, tenez compte des points suivants :

- Si vous supprimez des paramètres étendus à un service, la jonction SIP gérée par ces paramètres est gérée par les paramètres appliqués à son site, le cas échéant. En l’absence de paramètres de site, la jonction est gérée par la collection globale de paramètres de configuration de jonction.
- Si vous supprimez des paramètres étendus à un site, les jonctions SIP gérées par ces paramètres sont alors gérées par la collection globale de paramètres de configuration de jonction.

**Pour supprimer les paramètres de configuration de jonction à l’aide du panneau de configuration Skype entreprise Server** 

1. Dans le panneau de configuration de Skype entreprise Server, cliquez sur **routage des communications vocales**, puis sur Configuration de la **jonction**.
2. Dans l’onglet Configuration de la **jonction** , sélectionnez la collection de paramètres de configuration de jonction SIP à supprimer, cliquez sur **modifier**, puis sur **supprimer**. Pour supprimer plusieurs collections en une seule opération, cliquez sur la première collection à supprimer, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres collections à supprimer.
3. La propriété **État** de la collection est mise à jour et présente la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Valider tout**.
4. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.
5. Dans la boîte de dialogue **panneau de configuration de Skype entreprise Server** , cliquez sur **OK**.
6. Si vous changez d’avis et décidez de ne pas supprimer la collection, cliquez sur **valider**, puis sur **Annuler toutes les modifications non validées**. Lorsque la boîte de dialogue **panneau de configuration de Skype entreprise Server** s’affiche, cliquez sur **OK**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration de jonction à l’aide des applets de commande Windows PowerShell


Vous pouvez supprimer les paramètres de configuration de jonction à l’aide de Windows PowerShell et de l’applet de commande **Remove-applet cstrunkconfiguration** . Vous pouvez exécuter cette cmdlet à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 

**Pour supprimer une collection de paramètres spécifiée**

La commande suivante supprime les paramètres de configuration de jonction appliqués au site Redmond :

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**Pour supprimer toutes les collections appliquées à l’étendue site**

Cette commande supprime tous les paramètres de configuration de jonction appliqués dans l’étendue du site :

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**Pour supprimer toutes les collections pour lesquelles la déviation du trafic multimédia est activée**

La commande suivante supprime tous les paramètres de configuration de jonction dès lors que le contournement de média est activé :

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-applet cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) .
