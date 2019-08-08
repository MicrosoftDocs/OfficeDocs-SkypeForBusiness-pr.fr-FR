---
title: Configurer les paramètres de parc d’appels dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modifiez les paramètres de parc d’appels dans Skype entreprise Server Voice.
ms.openlocfilehash: df7334734784a773abd1df66a7544c3141a9aec9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233706"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>Configurer les paramètres de parc d’appels dans Skype entreprise

Modifiez les paramètres de parc d’appels dans Skype entreprise Server Voice.

Si vous ne voulez pas utiliser les paramètres de parc d’appels par défaut, vous pouvez les personnaliser. Lorsque vous installez l’application de parc d’appels, les paramètres globaux sont configurés par défaut. Vous pouvez modifier les paramètres généraux et définir également des paramètres spécifiques à un site. L’applet de commande **New-CsCpsConfiguration** permet de créer des paramètres spécifiques à un site. L’applet de commande **Set-CsCpsConfiguration** permet de modifier les paramètres existants.

> [!NOTE]
> Nous vous recommandons de configurer au moins l’option **OnTimeoutURI** pour la destination de remplacement à utiliser lorsqu’un appel parqué échoue.

Les applets de commande **New-CsCpsConfiguration** et **Set-CsCpsConfiguration** permettent de configurer les paramètres suivants :


| **Cette option :**                     | **Spécifie cet élément :**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | Période qui s’écoule entre le moment où un appel est parqué et le moment où il sonne de nouveau sur le téléphone auquel il était destiné.  <br/> La valeur doit être entrée au format hh:mm:ss (heures, minutes, secondes). La valeur minimale est de 10 secondes et la valeur maximale, de 10 minutes. La valeur par défaut est 00:01:30.  <br/> |
| **EnableMusicOnHold** <br/>          | Si une musique est diffusée pour l’appelant pendant le parcage d’un appel.  <br/> Les valeurs sont True ou False. La valeur par défaut est True.  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | Nombre de sonnerie de rappel d’un appel parqué avant qu’il soit transféré vers l’URI de remplacement spécifié pour le paramètre **OnTimeoutURI**. La valeur par défaut est 1.<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | Adresse SIP (Session Initiation Protocol) de l’utilisateur ou groupe Response Group vers laquelle l’appel parqué sans réponse est routé lorsque la valeur **MaxCallPickupAttempts** est atteinte. <br/> La valeur doit être une URI SIP (Session Initiation Protocol) et commencer par la chaîne « sip: ». Par exemple, sip:bob@contoso.com. La valeur par défaut est aucune adresse de transfert.<br/>                                                   |

### <a name="to-configure-call-park-settings"></a>Pour configurer les paramètres du parc d’appels

1. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.

2. Exécutez :

   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > L’applet de commande **Get-CsSite** permet d’identifier le site. Pour plus d’informations, reportez-vous à la documentation Skype entreprise Server Management Shell.

    Par exemple :

   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>Voir aussi

[Personnalisation de l’attente musicale du parcage d’appel dans Skype Entreprise 2015](customize-call-park-music-on-hold.md)

[Nouveau-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
