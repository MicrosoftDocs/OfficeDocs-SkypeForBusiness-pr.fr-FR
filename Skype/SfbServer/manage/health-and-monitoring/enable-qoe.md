---
title: Activer la qualité de l’expérience dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Résumé : Découvrez comment activer la qualité de l’expérience (QoE) dans Skype Entreprise Server.'
ms.openlocfilehash: 5865417582f2676525e955efd800684647d9a191
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580588"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>Activer la qualité de l’expérience dans Skype Entreprise Server

**Résumé : Découvrez comment** activer la qualité de l’expérience (QoE) dans Skype Entreprise Server.

La qualité de l’expérience (QoE) enregistre des données numériques qui indiquent la qualité du média, ainsi que les informations sur les participants, les noms des appareils, les pilotes, les adresses IP et les types de point de terminaison impliqués dans les appels et les sessions. Pour plus d’informations, voir [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) dans la documentation de planification.

Procédez comme suit pour activer la QoE dans toute l’entreprise ou dans chacun de ses sites.

> [!NOTE]
> Pour activer la qualité de l’expérience, vous devez commencer par configurer la surveillance et une base de données principale de surveillance. Pour plus d’informations, voir [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>Pour activer QoE à l’aide du Skype Entreprise Server de contrôle

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Données de qualité de l’expérience**.

4. Dans la page **Données de qualité de l’expérience**, cliquez sur la collection appropriée dans le tableau, sur **Action**, puis sur **Activer QoE**.

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Activation de la QoE à l’aide Windows PowerShell cmdlets

Vous pouvez activer la QoE à l’Windows PowerShell et à l’aide de **l';set-CsQoEConfiguration.)** Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour vous connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : Gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ». Le processus est le même dans Skype Entreprise Server.

### <a name="to-enable-qoe-for-a-single-location"></a>Pour activer la qualité de l’expérience pour un emplacement

 Pour activer la qualité de l’expérience, définissez le paramètre EnableQoE sur True ($True).

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>Pour désactiver la qualité de l’expérience pour un emplacement

 Pour désactiver la qualité de l’expérience, définissez le paramètre EnableQoE sur False ($False). Ceci ne désinstalle pas la surveillance, mais suspend la collecte et le stockage des données de qualité de l’expérience.

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>Pour utiliser une commande pour activer la qualité de l’expérience dans plusieurs emplacements

 Cette commande active la qualité de l’expérience pour tous les paramètres de configuration QoE actuellement utilisés dans votre organisation.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

Pour plus d’informations, [voir Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).

## <a name="see-also"></a>Voir aussi

[Planification de la surveillance](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[Déploiement du serveur de surveillance](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)