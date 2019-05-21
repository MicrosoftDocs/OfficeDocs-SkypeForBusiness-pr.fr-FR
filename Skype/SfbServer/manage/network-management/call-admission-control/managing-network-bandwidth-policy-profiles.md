---
title: Gestion des profils de stratégie de bande passante réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Les procédures décrites dans cet article vous permettent d’afficher, de créer, de modifier ou de supprimer des profils de stratégie de bande passante réseau.
ms.openlocfilehash: 3b2b62e5e823a9d86f1884d79b67483bce38a39f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279521"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Gestion de profils de stratégie de bande passante réseau dans Skype Entreprise Server

Les procédures décrites dans cet article vous permettent d’afficher, de créer, de modifier ou de supprimer des profils de stratégie de bande passante réseau.

## <a name="view-network-bandwidth-policy-profile-information"></a>Afficher les informations de profil de la stratégie de bande passante réseau

Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée pour définir des limitations de bande passante pour certaines modalités. Dans Skype entreprise Server, seules les modalités d’audio et de vidéo peuvent être affectées par des limitations de bande passante. Vous pouvez définir les limites générales de bande passante et les limites de session. Le panneau de configuration Skype entreprise Server vous permet de créer, modifier ou supprimer un profil de conteneur pour ces stratégies. Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau. Pour afficher le profil d’une stratégie de bande passante, procédez comme suit. 

### <a name="to-view-a-bandwidth-policy-profile"></a>Pour afficher un profil de stratégie de bande passante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **stratégie de bande passante**.

4.  Dans la page **stratégie de bande passante** , cliquez sur le profil de la stratégie de bande passante que vous souhaitez afficher.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de profil de la stratégie de bande passante du réseau à l’aide des cmdlets Windows PowerShell

Les profils de bande passante réseau peuvent être affichés à l’aide de Windows PowerShell et de l’applet de connexion Get-CsNetworkBandwidthPolicyProfile. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>Pour afficher les informations de profil de la stratégie de bande passante réseau

  - Pour afficher des informations sur tous les profils de votre stratégie de bande passante réseau, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .


## <a name="create-or-modify-bandwidth-policy-profiles"></a>Créer ou modifier des profils de stratégie de bande passante

Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée pour définir des limitations de bande passante pour certaines modalités. Dans Skype entreprise Server, seules les modalités d’audio et de vidéo peuvent être affectées par des limitations de bande passante. Vous pouvez définir les limites générales de bande passante et les limites de session. Le panneau de configuration Skype entreprise Server vous permet de créer, modifier ou supprimer un profil de conteneur pour ces stratégies. Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau. Pour créer ou modifier un profil de stratégie de bande passante, procédez comme suit. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>Pour créer un profil de stratégie de bande passante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **stratégie de bande passante**.

4.  Dans la page **stratégie de bande passante** , cliquez sur **nouveau**.

5.  Dans **nouveau profil de stratégie de bande passante**, tapez un nom dans le champ **nom** . Ce nom doit être unique parmi tous les profils de stratégie de bande passante.

6.  Dans le champ **limite audio** , entrez une valeur numérique. Cette valeur correspond au nombre maximal de bande passante à allouer pour toutes les connexions audio, exprimée en kbps.

7.  Entrez une valeur numérique dans le champ **limite de session audio** . Cette valeur correspond au volume maximal de bande passante à allouer pour une connexion audio individuelle, exprimée en kbps. Cette valeur doit être 40 ou une version ultérieure.

8.  Entrez une valeur numérique dans le champ **limite vidéo** . Cette valeur correspond au volume maximal de bande passante à allouer pour toutes les connexions vidéo, exprimée en kbps.

9.  Entrez une valeur numérique dans le champ **limite de session vidéo** . Cette valeur correspond au volume maximal de bande passante à allouer pour une connexion vidéo individuelle, exprimée en kbps. Cette valeur doit être 100 ou une version ultérieure.

10. Facultatif Tapez une valeur dans le champ **Description** pour fournir des informations supplémentaires sur le profil de la stratégie de bande passante qui ne peut pas être exprimé uniquement par le nom.

11. Cliquez sur **Valider**.

    > [!NOTE]  
    > La création d’un profil de stratégie de bande passante n’applique pas automatiquement les restrictions de bande passante. Vous devez d’abord associer le profil de la stratégie à un site. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>Pour modifier le profil d’une stratégie de bande passante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **stratégie de bande passante**.

4.  Dans la page **stratégie de bande passante** , cliquez sur le profil de la stratégie de bande passante que vous voulez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **modifier le profil de la stratégie de bande passante** , modifiez les champs si nécessaire (pour plus de détails, voir [créer un profil de stratégie de bande passante](#to-create-a-new-bandwidth-policy-profile)).

7.  Cliquez sur **Valider**.

    > [!NOTE]  
    > Lorsque vous modifiez le profil de la stratégie de bande passante, il met à jour immédiatement les limites de bande passante pour tous les sites réseau associés à ce profil de stratégie de bande passante.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Supprimer les profils de stratégie de bande passante réseau

Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée pour définir des limitations de bande passante pour certaines modalités. Dans Skype entreprise Server, seules les modalités d’audio et de vidéo peuvent être affectées par des limitations de bande passante. Vous pouvez définir les limites générales de bande passante et les limites de session. Le panneau de configuration Skype entreprise Server vous permet de créer, modifier ou supprimer un profil de conteneur pour ces stratégies. Utilisez les procédures suivantes pour supprimer un profil de stratégie de bande passante réseau. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>Pour supprimer un profil de stratégie de bande passante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **stratégie de bande passante**.

4.  Dans la page **stratégie de bande passante** , cliquez sur le profil de la stratégie de bande passante que vous voulez supprimer.

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs profils à la fois. Pour cela, appuyez sur CTRL et sélectionnez plusieurs profils tout en maintenant la touche CTRL enfoncée. Pour sélectionner tous les profils, dans le menu **Edition** , cliquez sur **Sélectionner tout** .

5.  Dans le menu **modifier** , cliquez sur **supprimer**.
   

    > [!WARNING]  
    > Vous ne pouvez pas supprimer un profil de stratégie de bande passante associé à un site réseau. Vous devez d’abord supprimer l’Association au site du réseau avant de pouvoir supprimer le profil. 


## <a name="see-also"></a>Voir aussi

[Gestion du contrôle d’admission des appels pour les sites](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

