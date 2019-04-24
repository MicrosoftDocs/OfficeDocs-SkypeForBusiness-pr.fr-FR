---
title: Activer l’enregistrement des détails des appels dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Résumé : Découvrez comment activer des détails des appels (CDR) enregistrements dans Skype pour Business Server.'
ms.openlocfilehash: 8ba053c95dcb9e43b6951671853d2c064ad5542f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199713"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Activer l’enregistrement des détails des appels dans Skype pour Business Server

**Résumé :** Découvrez comment activer des détails des appels (CDR) enregistrements dans Skype pour Business Server.

La fonctionnalité d’enregistrement des détails des appels recense des informations d’utilisation et de diagnostic sur les activités d’égal à égal, telles que la messagerie instantanée, les appels VoIP (Voice over Internet Protocol), le partage d’application, le transfert de fichiers et les réunions. Vous pouvez utiliser les données d’utilisation pour calculer le retour sur investissement (ROI) et les données de diagnostic pour résoudre les problèmes liés aux activités d’égal à égal et aux réunions.

Procédez comme suit pour activer l’enregistrement des détails des appels dans toute l’organisation ou dans chacun de ses sites.

> [!NOTE]
> Pour activer l’enregistrement des détails des appels, vous devez configurer la surveillance et une base de données de surveillance. Pour plus d’informations, voir [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Pour activer des détails des appels avec Skype pour Business Server Control Panel

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.

3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.

4. Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans la table, sur **Action**, puis sur **Activer l’enregistrement des détails des appels**.

    > [!NOTE]
    > Cette fonctionnalité est activée par défaut.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Activation des détails des appels à l’aide des applets de commande Windows PowerShell

Vous pouvez activer des détails des appels à l’aide de Windows PowerShell et l’applet de commande **Set-CsCdrConfiguration** . Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.

### <a name="to-enable-cdr-for-a-single-location"></a>Pour activer l’enregistrement des détails des appels pour un seul site

 Pour désactiver l’enregistrement des détails des appels, attribuez au paramètre EnableCDR la valeur True ($True).

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Pour désactiver l’enregistrement des détails des appels pour un seul site

 Pour désactiver l’enregistrement des détails des appels, attribuez au paramètre EnableCDR la valeur False ($False). Cette désactivation n’a pas pour effet de désinstaller la surveillance ; il interrompt la collecte et le stockage des données d’enregistrement des détails des appels.

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Pour activer l’enregistrement des détails des appels sur plusieurs sites en une seule commande

 Cette commande active l’enregistrement des détails des appels pour tous les paramètres de configuration de l’enregistrement des détails des appels utilisés dans votre organisation.

  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True
  ```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .

## <a name="see-also"></a>Voir aussi

[Planification de la surveillance](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
