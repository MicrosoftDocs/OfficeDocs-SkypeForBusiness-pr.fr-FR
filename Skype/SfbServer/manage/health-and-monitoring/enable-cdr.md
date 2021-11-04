---
title: Activer l’enregistrement des détails des appels dans Skype Entreprise Server
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
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Résumé : Découvrez comment activer les enregistrements des détails des appels dans Skype Entreprise Server.'
ms.openlocfilehash: 7adfc44c97387fc99244b0d2dea1cd7f884b6e6e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740580"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Activer l’enregistrement des détails des appels dans Skype Entreprise Server

**Résumé :** Découvrez comment activer les enregistrements des détails des appels dans Skype Entreprise Server.

La fonctionnalité d’enregistrement des détails des appels recense des informations d’utilisation et de diagnostic sur les activités d’égal à égal, telles que la messagerie instantanée, les appels VoIP (Voice over Internet Protocol), le partage d’application, le transfert de fichiers et les réunions. Vous pouvez utiliser les données d’utilisation pour calculer le retour sur investissement (ROI) et les données de diagnostic pour résoudre les problèmes liés aux activités d’égal à égal et aux réunions.

Procédez comme suit pour activer l’enregistrement des détails des appels dans toute l’organisation ou dans chacun de ses sites.

> [!NOTE]
> Pour activer l’enregistrement des détails des appels, vous devez configurer la surveillance et une base de données de surveillance. Pour plus d’informations, voir [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Pour activer l’cdr avec Skype Entreprise Server panneau de commande

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.

4. Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans la table, sur **Action**, puis sur **Activer l’enregistrement des détails des appels**.

    > [!NOTE]
    > Cette fonctionnalité est activée par défaut.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Activation de l’cdr à l’Windows PowerShell cmdlets

Vous pouvez activer l’Windows PowerShell à l’aide de **l’Windows PowerShell set-CsCdrConfiguration.** Vous pouvez exécuter cette cmdlet à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype Entreprise Server, voir [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Le processus est le même dans Skype Entreprise Server.

### <a name="to-enable-cdr-for-a-single-location"></a>Pour activer l’enregistrement des détails des appels pour un seul site

 Pour désactiver l’enregistrement des détails des appels, attribuez au paramètre EnableCDR la valeur True ($True).

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Pour désactiver l’enregistrement des détails des appels pour un seul site

 Pour désactiver l’enregistrement des détails des appels, attribuez au paramètre EnableCDR la valeur False ($False). La désactivation de l’cdr ne désinstalle pas la surveillance. Elle interrompt la collecte et le stockage des données d’cdr.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Pour activer l’enregistrement des détails des appels sur plusieurs sites en une seule commande

 Cette commande active l’enregistrement des détails des appels pour tous les paramètres de configuration de l’enregistrement des détails des appels utilisés dans votre organisation.

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

Pour plus d’informations, voir la rubrique d’aide de [l';set-CsCdrConfiguration.)](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)

## <a name="see-also"></a>Voir aussi

[Planification de la surveillance](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[Déploiement du serveur de surveillance](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)