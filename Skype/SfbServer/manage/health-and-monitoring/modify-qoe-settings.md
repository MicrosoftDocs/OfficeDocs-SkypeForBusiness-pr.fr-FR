---
title: Modifier les paramètres de qualité de l’expérience dans Skype Entreprise Server
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
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Résumé : Découvrez comment spécifier la rétention des données QoE dans Skype Entreprise Server.'
ms.openlocfilehash: 38bc88866e4bd8b677873b2d502e9268305ccf49
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770242"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Modifier les paramètres de qualité de l’expérience dans Skype Entreprise Server

**Résumé :** Découvrez comment spécifier la rétention des données QoE dans Skype Entreprise Server.

Par défaut, les données de qualité de l’expérience (QoE) sont vidées au bout de 60 jours. Vous pouvez utiliser les paramètres de la page **Données de qualité de l’expérience** pour conserver les données pendant une période plus longue ou plus courte. Si vous désactivez QoE, les données capturées avant que l’activation de QoE seront également purgées.

> [!NOTE]
> Vous devez configurer l’enregistrement des détails des appels (CDR) et QoE pour conserver des données pendant le même nombre de jours. Chaque appel des enregistrements des détails des appels disponible à partir de la page d’accueil des rapports de surveillance inclut des informations sur l’enregistrement des détails des appels et sur la qualité de l’expérience. Si la durée du vidage est différente pour les enregistrements des détails des appels (CDR) et la qualité de l’expérience (QoE), certains appels pourront inclure uniquement des données CDR, tandis que d’autres contiendront uniquement des données QoE.

La procédure suivante décrit comment configurer des paramètres de vidage pour des données de qualité de l’expérience (QoE).

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Pour spécifier la rétention des données QoE à l’aide du Skype Entreprise Server de contrôle

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus de détails, voir **Déléguer des autorisations de configuration**.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.

4. A la page **Données de qualité de l’expérience**, cliquez sur le site approprié dans le tableau, sur **Modifier**, puis sur **Afficher les détails**.

5. Pour activer le vidage, sélectionnez **Activer le vidage des données de qualité de l’expérience**.

6. Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximal de jours pendant lesquels les données de qualité de l’expérience doivent être conservées.

7. Cliquez sur **Valider**.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Spécification de la rétention QoE à l’aide Windows PowerShell cmdlets

Vous pouvez créer des paramètres de rétention QoE à l’aide de Windows PowerShell et de l’cmdlet **Set-CsQoEConfiguration.** Vous pouvez exécuter cette cmdlet à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype Entreprise Server, voir [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Le processus est le même dans Skype Entreprise Server.

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>Pour spécifier la conservation des données QoE pour un emplacement spécifique

- Cette commande active le vidage des données QoE pour le site Redmond et configure le site de façon à conserver les données QoE pendant 20 jours.

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>Pour spécifier la conservation des données QoE pour plusieurs emplacements

- Cette commande configure la conservation des données QoE pour tous les paramètres de configuration QoE utilisés dans une organisation.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Set-CsQoEConfiguration.](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)

## <a name="see-also"></a>Voir aussi

[Déploiement du serveur de surveillance](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)