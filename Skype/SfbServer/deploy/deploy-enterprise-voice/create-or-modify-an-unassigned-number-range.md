---
title: Créer ou modifier une plage de numéro non Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Créez, modifiez ou supprimez des plages de numéro non Skype Entreprise Server Voix Entreprise. Cela affecte la façon dont les appels vers des numéros non affectés sont gérés.
ms.openlocfilehash: 10e65d6202babd0c15fe569c71f6e8a84b301eb7
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410547"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>Créer ou modifier une plage de numéro non Skype Entreprise Server
 
Créez, modifiez ou supprimez des plages de numéro non Skype Entreprise Server Voix Entreprise. Cela affecte la façon dont les appels vers des numéros non affectés sont gérés.
  
Skype Entreprise Server vous permet de dire ce qu’il advient des appels entrants vers des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Pour gérer ces appels, vous devez configurer une table des chiffres non gérés. Vous pouvez utiliser le tableau pour router les appels vers une application d’annonce ou vers Exchange serveur de messagerie un peu plus rapide.
  
La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser. Vous pouvez configurer la table avec toutes les numéros de poste valides de votre organisation, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéros. La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle appelée uniquement lorsqu’un appelant compose un numéro qui n’est pas attribué. Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’organisation, sans avoir à reconfigurer la table. Si vous incluez des extensions non signées dans le tableau, vous pouvez modifier l’action qui se produit pour des numéros spécifiques. Par exemple, si vous modifiez le poste de votre service clientèle, vous pouvez inclure l’ancien numéro de service clientèle dans la table, puis l’affecter à une annonce qui fournit le nouveau numéro.
  
## <a name="configure-unassigned-phone-numbers"></a>Configurer des numéros de téléphone non assignés

Utilisez l’une des procédures suivantes pour configurer des plages de numéro non assignés pour l’application Annonce.
  
> [!IMPORTANT]
> Avant de configurer la table des chiffres non définis, les annonces doivent déjà être définies dans votre système ou une Standard automatique de messagerie unifiée Exchange. 
  
> [!TIP]
> Lorsqu’une personne appelle un numéro non Skype Entreprise Server recherche la table des nombres non appariés de haut en bas et utilise la première plage correspondante. Par conséquent, une action que vous souhaitez effectuer en dernier recours doit être spécifiée pour la dernière plage du tableau. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>Pour utiliser Skype Entreprise Server de configuration pour configurer des numéros de téléphone non utilisés

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus de détails, voir **Déléguer des autorisations de configuration**.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Numéro non attribué**.
    
4. Dans la page **Numéro non attribué**, effectuez l’une des opérations suivantes :
    
   - Pour créer une nouvelle plage de numéros, cliquez sur **Nouveau**. Dans **Nom**, tapez le nom de cette plage de numéros.
    
     > [!NOTE]
     > Une fois que vous avez validé la nouvelle plage de numéros non attribués dans la base de données, vous ne pouvez plus modifier ce nom. 
  
   - Pour modifier une plage de numéros existante, tapez tout ou une partie du nom de la plage de numéros dans le champ de recherche. Dans la liste des plages de numéros résultante, cliquez sur celle voulue, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans le premier champ **Plage de numéros**, tapez le numéro de début de plage, puis dans le second champ **Plage de numéros**, tapez le numéro de fin de la plage.
    
   - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de celle-ci.
    
   - Si le numéro de début ou de fin de plage inclut un numéro de poste, les numéros de début et de fin de plage doivent inclure un poste, et le numéro d’extension doit être le même pour les numéros de début et de fin de plage.
    
   - Le nombre doit correspondre à l’expression régulière `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?`. `tel:` Cela signifie que le numéro peut commencer par la chaîne (si vous ne spécifiez pas cette chaîne, elle sera automatiquement ajoutée pour vous), un signe plus (+) et un chiffre de 1 à 9. Le numéro de téléphone peut comporter jusqu’à 17 chiffres et peut être suivi d’un poste au format ;ext= suivi du numéro de poste.
    
6. Dans **Service d’annonce**, effectuez l’une des opérations suivantes : 
    
   - Cliquez sur **Annonce**.
    
   - Cliquez sur **Messagerie unifiée Exchange**.
    
7. Si, dans l’étape précédente, vous avez cliqué sur **Annonce**, procédez comme suit :
    
    a. Sous **Nom de domaine complet du serveur de destination**, cliquez sur **Sélectionner**, cliquez sur l’ID de service du service Application qui exécute l’application Annonce devant gérer les appels entrants destinés à cette plage de numéros non attribués, puis sur **OK**.
    
    b. Dans **Annonce**, cliquez sur l’annonce à associer à cette plage de numéros non attribués.
    
8. Si, dans l’étape précédente, vous avez cliqué sur **Messagerie unifiée Exchange**, sous **Numéro de téléphone du standard automatique**, cliquez sur **Sélectionner**, puis sur le numéro de téléphone devant être utilisé par cette plage de numéros non attribués et cliquez sur **OK**.
    
9. Cliquez sur **OK**.
    
10. Dans la page **Numéro non attribué**, vérifiez que les plages de numéros non attribués apparaissent dans l’ordre voulu. Pour déplacer une plage dans la table, cliquez sur un ou plusieurs noms consécutifs dans la liste de plages, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!TIP]
    > Skype Entreprise Server recherche de haut en bas la table des nombres non assignés et utilise la première plage qui correspond au numéro non assigné. Si des plages se chevauchent et qu’une plage spécifie une action de dernier recours, vérifiez qu’elle se trouve en bas de la liste. 
  
11. Une fois que vous disposez des plages de numéros non attribués dans l’ordre souhaité, cliquez sur **Valider tout**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>Pour utiliser Skype Entreprise Server Management Shell pour configurer des numéros de téléphone non utilisés

1. Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.
    
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
3. Utilisez **New-CsUnassignedNumber** pour créer une plage de numéros non attribués. Utilisez **Set-CsUnassignedNumber** pour modifier une plage de numéros non attribués existante.
    
    > [!TIP]
    > Si des plages se chevauchent et vous souhaitez qu’elles soient appliquées dans un ordre spécifique, incluez le paramètre Priority. La plage dont la priorité est la plus élevée sera appliquée à l’appel. La valeur 0 représente la priorité la plus élevée.
  
    Sur la ligne de commande, effectuez l’une des opérations suivantes :
    
   - Pour créer une plage de numéros pour un service Annonces, exécutez :
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - Ou pour créer une plage de numéros pour le standard automatique de messagerie unifiée Exchange, exécutez :
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     Par exemple :
    
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

## <a name="delete-an-unnasigned-number-range"></a>Supprimer une plage de numéro non signés

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>Pour utiliser Skype Entreprise Server de contrôle d’accès pour supprimer une plage de numéro non utilisés

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus de détails, voir **Déléguer des autorisations de configuration**.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Numéro non attribué**.
    
4. Dans la page **Numéro non attribué**, dans le champ recherche, tapez entièrement ou partiellement le nom de la plage de numéros non attribués que vous voulez supprimer.
    
5. Dans la liste des plages de numéros résultante, cliquez sur le nom, cliquez sur **Modifier**, puis sur **Supprimer**.
    
6. Cliquez sur **Tout valider**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>Pour utiliser Skype Entreprise Server Management Shell pour supprimer une plage de numéro non utilisés

1. Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.
    
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
3. Sur la ligne de commande, tapez :
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    Par exemple :
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > Pour plus d’informations sur d’autres options, [voir Remove-CsCallParkOrbit](/powershell/module/skype/remove-cscallparkorbit?view=skype-ps). 
  
## <a name="see-also"></a>Voir aussi

[New-CsUnassignedNumber](/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](/powershell/module/skype/get-csunassignednumber?view=skype-ps)