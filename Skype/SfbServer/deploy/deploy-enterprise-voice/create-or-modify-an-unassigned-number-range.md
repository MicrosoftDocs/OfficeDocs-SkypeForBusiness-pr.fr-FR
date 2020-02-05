---
title: Création ou modification d’une plage de numéros non affectées dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Créer, modifier ou supprimer des plages de numéros non attribués pour l’application d’annonce dans Skype entreprise Server Voice. Cela affecte le traitement des appels à des numéros non attribués.
ms.openlocfilehash: d357a97bffda50d6d387ba40a12f62dacac5ce31
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767747"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>Création ou modification d’une plage de numéros non affectées dans Skype entreprise Server
 
Créer, modifier ou supprimer des plages de numéros non attribués pour l’application d’annonce dans Skype entreprise Server Voice. Cela affecte le traitement des appels à des numéros non attribués.
  
Skype entreprise Server vous permet de dire ce qu’il advient des appels entrants vers des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Pour gérer ces appels, vous devez configurer une table de numéros non attribués. Vous pouvez utiliser le tableau pour acheminer les appels vers une application d’annonce ou vers un serveur de messagerie unifiée Exchange.
  
La manière dont vous configurez la table des numéros non attribués dépend de l’utilisation envisagée. Vous pouvez configurer la table avec tous les numéros de poste valides de votre organisation, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéro. La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle n’est appelée que lorsqu’un appelant compose un numéro qui n’est pas attribué. Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’organisation, sans avoir à reconfigurer la table. Si vous intégrez des numéros de poste non attribués à la table, vous pouvez modifier la réponse à certains numéros. Par exemple, si vous modifiez le numéro de poste de votre bureau de service client, vous pouvez inclure l’ancien numéro dans la table et l’attribuer à une annonce qui indique le nouveau numéro.
  
## <a name="configure-unassigned-phone-numbers"></a>Configuration des numéros de téléphone non attribués

Utilisez l’une des procédures suivantes pour configurer des plages de nombres non affectées pour l’application d’annonce.
  
> [!IMPORTANT]
> Avant de configurer la table des numéros non attribués, votre système doit déjà disposer d’annonces définies ou un standard automatique de messagerie unifiée (UM) est configuré. 
  
> [!TIP]
> Lorsque quelqu’un appelle un numéro non attribué, Skype entreprise Server effectue une recherche dans la table des numéros non attribués, de haut en bas, et utilise la première plage correspondante. Par conséquent, une action que vous voulez voir effectuée en dernier ressort doit être spécifiée pour la dernière plage de la table. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>Pour utiliser le panneau de configuration Skype entreprise Server pour configurer les numéros de téléphone non affectés

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez **autorisations de configuration de délégué**.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Numéro non attribué**.
    
4. Dans la page **Numéro non attribué**, effectuez l’une des opérations suivantes :
    
   - Pour créer une nouvelle plage de numéros, cliquez sur **Nouveau**. Dans **Nom**, tapez le nom de cette plage de numéros.
    
     > [!NOTE]
     > Une fois que vous avez validé la nouvelle plage de numéros non attribués dans la base de données, vous ne pouvez plus modifier ce nom. 
  
   - Pour modifier une plage de numéros existante, tapez tout ou une partie du nom de la plage de numéros dans le champ de recherche. Dans la liste des plages de numéros résultante, cliquez sur celle voulue, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans le premier champ **Plage de numéros**, tapez le numéro de début de plage, puis dans le second champ **Plage de numéros**, tapez le numéro de fin de la plage.
    
   - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.
    
   - Si le numéro de début ou de fin de plage inclut un numéro de poste, les numéros de début et de fin de plage doivent inclure un poste, et le numéro d’extension doit être le même pour les numéros de début et de fin de plage.
    
   - Le numéro doit correspondre à l’expression régulière (tel :) ? ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?. Cela signifie que le numéro peut commencer par la chaîne « tel : » (si vous ne spécifiez pas cette chaîne, elle sera automatiquement ajoutée pour vous), un signe plus (+) et un chiffre 1 à 9. Le numéro de téléphone peut comporter jusqu’à 17 chiffres et peut être suivi d’un poste au format ;ext= suivi du numéro de poste.
    
6. Dans **Service d’annonce**, effectuez l’une des opérations suivantes : 
    
   - Cliquez sur **Annonce**.
    
   - Cliquez sur **Messagerie unifiée Exchange**.
    
7. Si, dans l’étape précédente, vous avez cliqué sur **Annonce**, procédez comme suit :
    
    a. Sous **nom de domaine complet du serveur de destination**, cliquez sur **Sélectionner**, sur l’ID du service d’application exécutant l’application d’annonce qui traitera les appels entrants de cette plage de numéros non attribués, puis cliquez sur **OK**.
    
    b. Dans **Annonce**, cliquez sur l’annonce à associer à cette plage de numéros non attribués.
    
8. Si, dans l’étape précédente, vous avez cliqué sur **Messagerie unifiée Exchange**, sous **Numéro de téléphone du standard automatique**, cliquez sur **Sélectionner**, puis sur le numéro de téléphone devant être utilisé par cette plage de numéros non attribués et cliquez sur **OK**.
    
9. Cliquez sur **OK**.
    
10. Dans la page **Numéro non attribué**, vérifiez que les plages de numéros non attribués s’affichent dans l’ordre voulu. Pour déplacer une plage dans la table, cliquez sur un ou plusieurs noms consécutifs dans la liste de plages, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!TIP]
    > Skype entreprise Server effectue une recherche dans la table des numéros non attribués de haut en bas, et utilise la première plage qui correspond au numéro non attribué. Si des plages se chevauchent et qu’une plage spécifie une action de dernier recours, vérifiez qu’elle se trouve en bas de la liste. 
  
11. Une fois que vous disposez des plages de numéros non attribués dans l’ordre souhaité, cliquez sur **Valider tout**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>Pour utiliser Skype entreprise Server Management Shell pour configurer les numéros de téléphone non affectés

1. Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans **autorisations de configuration de délégué**.
    
2. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Utilisez **New-CsUnassignedNumber** pour créer une plage de numéros non attribués. Utilisez **Set-CsUnassignedNumber** pour modifier une plage de numéros non attribués existante.
    
    > [!TIP]
    > Si des plages se chevauchent et vous souhaitez qu’elles soient appliquées dans un ordre spécifique, incluez le paramètre Priority. La plage dont la priorité est la plus élevée sera appliquée à l’appel. La valeur 0 représente la priorité la plus élevée.
  
    Dans la ligne de commande, effectuez l’une des opérations suivantes :
    
   - Pour créer une plage de numéros pour un service Annonces, exécutez :
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - Ou pour créer une plage de numéros pour le standard automatique de messagerie unifiée Exchange, exécutez :
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     Exemple :
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     Ou
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     L’exemple suivant montre comment modifier les numéros d’une plage de numéros non attribués existante :
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>Suppression d’une plage de numéros non attribués

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>Pour utiliser le panneau de configuration Skype entreprise Server pour supprimer une plage de numéros non attribués

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez **autorisations de configuration de délégué**.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Numéro non attribué**.
    
4. Dans la page **Numéro non attribué**, dans le champ recherche, tapez entièrement ou partiellement le nom de la plage de numéros non attribués que vous voulez supprimer.
    
5. Dans la liste des plages de numéros résultante, cliquez sur le nom, cliquez sur **Modifier**, puis sur **Supprimer**.
    
6. Cliquez sur **Tout valider**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>Pour utiliser Skype entreprise Server Management Shell pour supprimer une plage de numéros non attribués

1. Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans **autorisations de configuration de délégué**.
    
2. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Dans la ligne de commande, tapez :
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    Par exemple :
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > Pour plus d’informations sur les autres options, voir [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps). 
  
## <a name="see-also"></a>Voir aussi

[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
