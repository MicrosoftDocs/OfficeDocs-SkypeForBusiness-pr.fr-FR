---
title: Gestion des profils de stratégie de bande passante réseau
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Utilisez les procédures dans cet article pour afficher, créer, modifier ou supprimer des profils de stratégie de bande passante réseau.
ms.openlocfilehash: 58a73774a55a64ac6cb81f0bdf887eb0d1493a35
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222939"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Gestion des profils de stratégie de bande passante réseau dans Skype pour Business Server

Utilisez les procédures dans cet article pour afficher, créer, modifier ou supprimer des profils de stratégie de bande passante réseau.

## <a name="view-network-bandwidth-policy-profile-information"></a>Afficher les informations de profil de stratégie de bande passante réseau

Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée pour définir des restrictions de bande passante pour des modes bien précis. Dans Skype pour Business Server, modalités uniquement audio et vidéos peuvent être attribuées à des limitations de bande passante. Vous pouvez définir des restrictions de bande passante globale et les limitations de session. Vous pouvez utiliser la Skype pour Business Server Control Panel pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies. Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites de réseau. Utilisez les procédures suivantes pour afficher un profil de stratégie de bande passante. 

### <a name="to-view-a-bandwidth-policy-profile"></a>Pour afficher un profil de stratégie de bande passante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau** , puis sur **Stratégie de bande passante**.

4.  Dans la page **Stratégie de bande passante** , cliquez sur le profil de stratégie de bande passante que vous souhaitez afficher.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de profil de stratégie de bande passante réseau à l’aide des applets de commande Windows PowerShell

Profils de bande passante réseau peuvent être affichés à l’aide de Windows PowerShell et l’applet de commande Get-CsNetworkBandwidthPolicyProfile. Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>Pour afficher les informations de profil de stratégie de bande passante réseau

  - Pour afficher des informations sur tous vos profils de stratégie de bande passante réseau, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .


## <a name="create-or-modify-bandwidth-policy-profiles"></a>Créer ou modifier des profils de stratégie de bande passante

Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée pour définir des restrictions de bande passante pour des modes bien précis. Dans Skype pour Business Server, modalités uniquement audio et vidéos peuvent être attribuées à des limitations de bande passante. Vous pouvez définir des restrictions de bande passante globale et les limitations de session. Vous pouvez utiliser la Skype pour Business Server Control Panel pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies. Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites de réseau. Utilisez les procédures suivantes pour créer ou modifier un profil de stratégie de bande passante. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>Pour créer un nouveau profil de stratégie de bande passante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Stratégie de bande passante**.

4.  Dans la page **Stratégie de bande passante** , cliquez sur **Nouveau**.

5.  Dans **Nouveau profil de stratégie de bande passante**, tapez un nom dans le champ **nom** . Ce nom doit être unique parmi tous les profils de stratégie de bande passante.

6.  Dans le champ **limite Audio** , tapez une valeur numérique. Cette valeur est la quantité maximale de bande passante à allouer pour toutes les connexions audio, exprimées en Kbits/s.

7.  Entrez une valeur numérique dans le champ de **limite de session Audio** . Cette valeur est la quantité maximale de bande passante à allouer pour une connexion audio individuelle, exprimée en Kbits/s. Cette valeur doit être 40 ou supérieur.

8.  Entrez une valeur numérique dans le champ **limite vidéo** . Cette valeur est la quantité maximale de bande passante à allouer pour toutes les connexions vidéo, exprimées en Kbits/s.

9.  Entrez une valeur numérique dans le champ de **limite de session vidéo** . Cette valeur est la quantité maximale de bande passante à allouer pour une connexion vidéo individuelle, exprimée en Kbits/s. Cette valeur doit être au moins 100.

10. (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce profil de stratégie de bande passante ne suffit pas au nom seul.

11. Cliquez sur **Valider**.

    > [!NOTE]  
    > Création d’un nouveau profil de stratégie de bande passante n’applique pas automatiquement les restrictions de bande passante. Vous devez d’abord associer le profil de stratégie à un site. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>Pour modifier un profil de stratégie de bande passante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Stratégie de bande passante**.

4.  Dans la page **Stratégie de bande passante** , cliquez sur le profil de stratégie de bande passante que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier un profil de stratégie de bande passante** , modifiez les champs comme il convient (pour plus d’informations, voir [créer un nouveau profil de stratégie de bande passante](#to-create-a-new-bandwidth-policy-profile)).

7.  Cliquez sur **Valider**.

    > [!NOTE]  
    > Lorsque vous modifiez le profil de stratégie de bande passante, il met immédiatement à jour les limitations de bande passante de tous les sites de réseau associés à ce profil de stratégie de bande passante.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Supprimer des profils de stratégie de bande passante réseau

Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée pour définir des restrictions de bande passante pour des modes bien précis. Dans Skype pour Business Server, modalités uniquement audio et vidéos peuvent être attribuées à des limitations de bande passante. Vous pouvez définir des restrictions de bande passante globale et les limitations de session. Vous pouvez utiliser la Skype pour Business Server Control Panel pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies. Utilisez les procédures suivantes pour supprimer un profil de stratégie de bande passante réseau. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>Pour supprimer un profil de stratégie de bande passante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Stratégie de bande passante**.

4.  Dans la page **Stratégie de bande passante** , cliquez sur le profil de stratégie de bande passante que vous souhaitez supprimer.

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs profils à la fois. Pour ce faire, appuyez sur la touche CTRL ENFONCÉE et sélectionnez plusieurs profils tout en maintenant la touche CTRL enfoncée. Ou, pour sélectionner tous les profils, cliquez sur **Sélectionner tout** dans le menu **Edition** .

5.  Dans le menu **Edition** , cliquez sur **Supprimer**.
   

    > [!WARNING]  
    > Vous ne pouvez pas supprimer un profil de stratégie de bande passante qui est associé à un site réseau. Vous devez d’abord supprimer l’association avec le site réseau avant de pouvoir supprimer le profil. 


## <a name="see-also"></a>Voir aussi

[Gérer le contrôle d’admission des appels pour les sites d’appel](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

