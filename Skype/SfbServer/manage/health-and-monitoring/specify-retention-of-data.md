---
title: Spécifier la rétention des données d’Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Résumé : Découvrez comment gérer les données d’enregistrement des détails des appels pour Skype Entreprise Server.'
ms.openlocfilehash: b232e853e28f2dbdee33c666e65ca89932796941
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852008"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>Spécifier la rétention des données d’Skype Entreprise Server
 
**Résumé :** Découvrez comment gérer les données d’enregistrement des détails des appels pour Skype Entreprise Server.
  
Par défaut, les données d’enregistrement des détails des appels sont vidées après un délai de 60 jours. Vous pouvez utiliser les paramètres de la page **Enregistrement des détails des appels** pour conserver les données pendant une période plus longue ou plus courte. Si vous désactivez la fonctionnalité d’enregistrement des détails des appels, les données capturées avant l’enregistrement seront également vidées.
  
> [!NOTE]
> Vous devez configurer l’enregistrement des détails des appels et la qualité de l’expérience (QoE) afin de conserver les données pendant le même nombre de jours. Chaque appel dans les rapports des détails des appels (disponibles à partir de la page web Rapports du serveur de surveillance) comprend des informations d’enregistrement des détails des appels et QoE. Si la durée de vidage pour les données d’enregistrement des détails des appels et de QoE est différente, certains appels peuvent inclure uniquement des données d’enregistrement des détails des appels et d’autres exclusivement des données QoE 
  
Utilisez les procédures suivantes pour configurer les paramètres de vidage des données d’enregistrement des détails des appels. 
  
### <a name="to-specify-retention-of-cdr-data"></a>Pour spécifier la conservation des données d’enregistrement des détails des appels

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.
    
4. Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans le tableau, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
5. Pour activer le vidage, sélectionnez **Activer le vidage des enregistrements des détails des appels**.
    
6. Dans **Conserver les enregistrements des détails des appels pendant la durée maximale (jours) :**, sélectionnez le nombre maximum de jours pendant lesquels les enregistrements des détails des appels sont à conserver.
    
7. Dans **Conserver les données de signalement d’erreurs pendant la durée maximale (jours) :**, sélectionnez le nombre maximum de jours pendant lesquels les rapports d’erreurs sont à conserver.
    
8. Cliquez sur **Valider**.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Spécification de la rétention des détails des détails des Windows PowerShell cmdlets

Vous pouvez définir les paramètres de conservation des enregistrements des détails des appels en utilisant Windows PowerShell et l’applet de commande Set-CsCdrConfiguration. Vous pouvez exécuter cette cmdlet à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype Entreprise Server, voir [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Le processus est le même dans Skype Entreprise Server.
  
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

Pour plus d’informations, voir la rubrique d’aide de [l';set-CsCdrConfiguration.)](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
## <a name="see-also"></a>Voir aussi

[Enregistrement des détails des appels dans Skype Entreprise Server](call-detail-recording-cdr.md)