---
title: Activer l’enregistrement des détails des appels dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Résumé : Découvrez comment activer les enregistrements des détails des appels dans Skype Entreprise Server.'
ms.openlocfilehash: 48d21be6d377df24e859c3ffa6bb8b7858076d29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816884"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Activer l’enregistrement des détails des appels dans Skype Entreprise Server

**Résumé :** Découvrez comment activer les enregistrements des détails des appels dans Skype Entreprise Server.

La fonctionnalité d’enregistrement des détails des appels recense des informations d’utilisation et de diagnostic sur les activités d’égal à égal, telles que la messagerie instantanée, les appels VoIP (Voice over Internet Protocol), le partage d’application, le transfert de fichiers et les réunions. Vous pouvez utiliser les données d’utilisation pour calculer le retour sur investissement (ROI) et les données de diagnostic pour résoudre les problèmes liés aux activités d’égal à égal et aux réunions.

Procédez comme suit pour activer l’enregistrement des détails des appels dans toute l’organisation ou dans chacun de ses sites.

> [!NOTE]
> Pour activer l’enregistrement des détails des appels, vous devez configurer la surveillance et une base de données de surveillance. Pour plus d’informations, voir [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Pour activer l’cdr avec le Panneau de contrôle Skype Entreprise Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.

4. Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans la table, sur **Action**, puis sur **Activer l’enregistrement des détails des appels**.

    > [!NOTE]
    > Cette fonctionnalité est activée par défaut.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Activation de l’cdr à l’Windows PowerShell cmdlets

Vous pouvez activer l’Windows PowerShell à l’aide de **l’Windows PowerShell l';Set-CsCdrConfiguration.)** Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ». Le processus est le même dans Skype Entreprise Server.

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

Pour plus d’informations, voir la rubrique d’aide de [l';set-CsCdrConfiguration.)](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)

## <a name="see-also"></a>Voir aussi

[Planification de la surveillance](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[Déploiement du serveur de surveillance](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
