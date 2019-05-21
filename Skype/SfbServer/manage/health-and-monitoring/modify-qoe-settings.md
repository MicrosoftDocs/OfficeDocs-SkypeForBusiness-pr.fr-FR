---
title: Modification des paramètres de qualité de l’expertise dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Résumé: Découvrez comment spécifier la conservation des données QoE dans Skype entreprise Server.'
ms.openlocfilehash: 89e20b18aa285bd4ee61df12c822e487dd6b37a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280004"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Modification des paramètres de qualité de l’expertise dans Skype entreprise Server

**Résumé:** Découvrez comment spécifier la conservation des données QoE dans Skype entreprise Server.

Par défaut, les données de qualité de l’expérience (QoE) sont vidées au bout de 60 jours. Vous pouvez utiliser les paramètres de la page **Données de qualité de l’expérience** pour conserver les données pendant une période plus longue ou plus courte. Si vous désactivez QoE, les données capturées avant que l’activation de QoE seront également purgées.

> [!NOTE]
> Vous devez configurer l’enregistrement des détails des appels (CDR) et QoE pour conserver des données pendant le même nombre de jours. Chaque appel des enregistrements des détails des appels disponible à partir de la page d’accueil des rapports de surveillance inclut des informations sur l’enregistrement des détails des appels et sur la qualité de l’expérience. Si la durée du vidage est différente pour les enregistrements des détails des appels (CDR) et la qualité de l’expérience (QoE), certains appels pourront inclure uniquement des données CDR, tandis que d’autres contiendront uniquement des données QoE.

La procédure suivante décrit comment configurer des paramètres de vidage pour des données de qualité de l’expérience (QoE).

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Pour spécifier la conservation des données QoE en utilisant le panneau de configuration Skype entreprise Server

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez **autorisations de configuration de délégué**.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.

4. Dans la page **Données de qualité de l’expérience**, cliquez sur le site approprié dans le tableau, sur **Modifier**, puis sur **Afficher les détails**.

5. Pour activer le vidage, sélectionnez **Activer le vidage des données de qualité de l’expérience**.

6. Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximal de jours pendant lesquels les données de qualité de l’expérience doivent être conservées.

7. Cliquez sur **Valider**.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Spécification de la rétention QoE en utilisant des applets de cmdlet Windows PowerShell

Vous pouvez créer des paramètres de rétention QoE à l’aide de Windows PowerShell et de l’applet **de cmdlet Set-CsQoEConfiguration** . Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [«démarrage rapide: gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype entreprise Server.

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>Pour spécifier la conservation des données QoE pour un emplacement spécifique

- Cette commande active le vidage des données QoE pour le site Redmond et configure le site de façon à conserver les données QoE pendant 20 jours.

  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>Pour spécifier la conservation des données QoE pour plusieurs emplacements

- Cette commande configure la conservation des données QoE pour tous les paramètres de configuration QoE utilisés dans une organisation.

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) .

## <a name="see-also"></a>Voir aussi

[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
