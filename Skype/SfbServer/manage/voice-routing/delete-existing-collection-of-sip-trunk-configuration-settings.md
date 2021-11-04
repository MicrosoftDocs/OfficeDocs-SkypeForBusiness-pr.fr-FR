---
title: Skype Entreprise Server - Supprimer une collection existante de paramètres de configuration de la trunk SIP
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. '
ms.openlocfilehash: 09e51dd54401b761c448872545111e8bebf01599
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760612"
---
# <a name="skype-for-business-server---delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>Skype Entreprise Server - Supprimer une collection existante de paramètres de configuration de la trunk SIP

Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :

- L’activation ou non du contournement de média sur les jonctions.
- Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).
- L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.

Lorsque vous installez Skype Entreprise Server, une collection globale de paramètres de configuration de la trunk SIP est créée pour vous. Cette collection globale de paramètres ne peut pas être supprimée. Toutefois, vous pouvez utiliser le panneau Skype Entreprise ServerControl ou l’cmdlet [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) pour « rétablir » les valeurs par défaut des propriétés de la collection globale. Par exemple, si vous avez définie la propriété Enable3pccRefer sur True, lorsque vous réinitialisez la collection globale, la propriété Enable3pccRefer rétablit sa valeur par défaut false.

Les administrateurs peuvent aussi créer des paramètres de configuration de jonction personnalisés étendus à un site ou un service (pour une passerelle PSTN individuelle) ; ces paramètres personnalisés peuvent être supprimés. Au moment de supprimer ces paramètres personnalisés, tenez compte des points suivants :

- Si vous supprimez des paramètres étendus à un service, la jonction SIP gérée par ces paramètres est gérée par les paramètres appliqués à son site, le cas échéant. En l’absence de paramètres de site, la jonction est gérée par la collection globale de paramètres de configuration de jonction.
- Si vous supprimez des paramètres étendus à un site, les jonctions SIP gérées par ces paramètres sont alors gérées par la collection globale de paramètres de configuration de jonction.

**Pour supprimer les paramètres de configuration de la Skype Entreprise Server panneau de configuration** 

1. Dans le Skype Entreprise Server de configuration, cliquez sur **Routage** des voix, puis sur **Configuration de la trunk .**
2. Sous **l’onglet Configuration** de la trunk, sélectionnez la collection de paramètres de configuration de la trunk SIP à supprimer, cliquez sur **Modifier,** puis cliquez sur **Supprimer**. Pour supprimer plusieurs collections en une seule opération, cliquez sur la première collection à supprimer, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres collections à supprimer.
3. La propriété **État** de la collection est mise à jour et présente la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Valider tout**.
4. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.
5. Dans la **boîte Skype Entreprise Server panneau de bord,** cliquez sur **OK.**
6. Si vous changez d’avis et décidez de ne pas supprimer la collection, cliquez sur **Valider,** puis cliquez sur Annuler toutes les modifications **non émises.** Lorsque la **boîte Skype Entreprise Server panneau de Skype Entreprise Server** s’affiche, cliquez sur **OK.**

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration de la Windows PowerShell cmdlets


Vous pouvez supprimer les paramètres de configuration de la Windows PowerShell à l’aide de l’cmdlet **Remove-CsTrunkConfiguration.** Vous pouvez exécuter cette cmdlet à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 

**Pour supprimer une collection spécifiée de paramètres**

La commande suivante supprime les paramètres de configuration de jonction appliqués au site Redmond :

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**Pour supprimer toutes les collections appliquées à l’étendue Site**

Cette commande supprime tous les paramètres de configuration de jonction appliqués dans l’étendue du site :

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**Pour supprimer toutes les collections où le contournement de média est activé**

La commande suivante supprime tous les paramètres de configuration de jonction dès lors que le contournement de média est activé :

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Remove-CsTrunkConfiguration.](/powershell/module/skype/Remove-CsTrunkConfiguration)
