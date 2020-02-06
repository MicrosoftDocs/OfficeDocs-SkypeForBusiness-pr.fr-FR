---
title: Spécifier la conservation des données CDR dans Skype entreprise Server
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
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Résumé : Découvrez comment gérer les données d’enregistrement des détails des appels pour Skype entreprise Server.'
ms.openlocfilehash: 7cb9926ee8ec124b2fc75a69653c43c0150b6446
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817673"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>Spécifier la conservation des données CDR dans Skype entreprise Server
 
**Résumé :** Apprenez à gérer les données d’enregistrement des détails des appels pour Skype entreprise Server.
  
Par défaut, les données d’enregistrement des détails des appels sont vidées après un délai de 60 jours. Vous pouvez utiliser les paramètres de la page **Enregistrement des détails des appels** pour conserver les données pendant une période plus longue ou plus courte. Si vous désactivez la fonctionnalité d’enregistrement des détails des appels, les données capturées avant l’enregistrement seront également vidées.
  
> [!NOTE]
> Vous devez configurer l’enregistrement des détails des appels et la qualité de l’expérience (QoE) afin de conserver les données pendant le même nombre de jours. Chaque appel dans les rapports des détails des appels (disponibles à partir de la page web Rapports du serveur de surveillance) comprend des informations d’enregistrement des détails des appels et QoE. Si la durée de vidage pour les données d’enregistrement des détails des appels et de QoE est différente, certains appels peuvent inclure uniquement des données d’enregistrement des détails des appels et d’autres exclusivement des données QoE. 
  
Utilisez les procédures suivantes pour configurer les paramètres de vidage des données d’enregistrement des détails des appels. 
  
### <a name="to-specify-retention-of-cdr-data"></a>Pour spécifier la conservation des données d’enregistrement des détails des appels

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.
    
4. Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans le tableau, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
5. Pour activer le vidage, sélectionnez **Activer le vidage des enregistrements des détails des appels**.
    
6. Dans **Conserver les enregistrements des détails des appels pendant la durée maximale (jours) :**, sélectionnez le nombre maximum de jours pendant lesquels les enregistrements des détails des appels sont à conserver.
    
7. Dans **Conserver les données de signalement d’erreurs pendant la durée maximale (jours) :**, sélectionnez le nombre maximum de jours pendant lesquels les rapports d’erreurs sont à conserver.
    
8. Cliquez sur **Valider**.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Spécification de la rétention CDR en utilisant des applets de cmdlet Windows PowerShell

Vous pouvez créer des paramètres de rétention CDR à l’aide de Windows PowerShell et de l’applet de cmdlet Set-CsCdrConfiguration. Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype entreprise Server.
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>Pour spécifier la conservation des enregistrements des détails des appels pour un emplacement particulier

- Cette commande vide les enregistrements des détails des appels pour le site de Redmond, et configure ce site pour qu’il conserve les enregistrements des détails des appels et les données de signalement d’erreurs pendant 20 jours.
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>Pour spécifier la conservation des enregistrements des détails des appels pour plusieurs emplacements

- Cette commande configure la conservation des enregistrements des détails des appels pour tous les paramètres de configuration des enregistrements des détails des appels actuellement appliqués dans l’organisation.
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Voir aussi

[Enregistrement des détails des appels (CDR) dans Skype entreprise Server](call-detail-recording-cdr.md)
