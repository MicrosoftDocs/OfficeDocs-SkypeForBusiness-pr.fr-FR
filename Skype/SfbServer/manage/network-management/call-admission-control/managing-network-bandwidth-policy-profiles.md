---
title: Gestion des profils de stratégie de bande passante réseau
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
description: Utilisez les procédures de cet article pour afficher, créer, modifier ou supprimer des profils de stratégie de bande passante réseau.
ms.openlocfilehash: fee0d4f57847747b0e25c98bc99183daa22a9996
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850997"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Gestion de profils de stratégie de bande passante réseau dans Skype Entreprise Server

Utilisez les procédures de cet article pour afficher, créer, modifier ou supprimer des profils de stratégie de bande passante réseau.

## <a name="view-network-bandwidth-policy-profile-information"></a>Afficher les informations de profil de stratégie de bande passante réseau

La stratégie de bande passante utilisée dans le cadre du contrôle d’admission des appels (CAC) permet de définir des restrictions de bande passante pour des modes bien précis. Dans Skype Entreprise Server, seules les modalités audio et vidéo peuvent être affectées à des restrictions de bande passante. Vous pouvez définir des restrictions de bande passante et de session globales. Vous pouvez utiliser le Panneau de Skype Entreprise Server pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies. Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau. Utilisez les procédures suivantes pour afficher un profil de stratégie de bande passante. 

### <a name="to-view-a-bandwidth-policy-profile"></a>Pour afficher un profil de stratégie de bande passante

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie de bande passante**.

4.  Dans la page **Stratégie de bande** passante, cliquez sur le profil de stratégie de bande passante à afficher.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de profil de stratégie de bande passante réseau à l’Windows PowerShell cmdlets

Vous pouvez afficher les profils de bande passante réseau à l’Windows PowerShell l'Get-CsNetworkBandwidthPolicyProfile cmdlet. Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>Pour afficher les informations de profil de stratégie de bande passante réseau

  - Pour afficher des informations sur tous vos profils de stratégie de bande passante réseau, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
    **Get-CsNetworkBandwidthPolicyProfile**
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
    Identity : RedmondBandwidthPolicy<br/>
    BWPolicy : {BWLimit=200; BWSessionLimit=200;<br/>
                        BWPolicyModality=Audio, <br/>
                        BWLimit=1400; BWSessionLimit=500;<br/>
                        BWPolicyModality=Video}<br/>
    BWPolicyProfileID : RedmondBandwidthPolicy<br/>
    Description :

Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Get-CsNetworkBandwidthPolicyProfile.](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)


## <a name="create-or-modify-bandwidth-policy-profiles"></a>Créer ou modifier des profils de stratégie de bande passante

La stratégie de bande passante utilisée dans le cadre du contrôle d’admission des appels (CAC) permet de définir des restrictions de bande passante pour des modes bien précis. Dans Skype Entreprise Server, seules les modalités audio et vidéo peuvent être affectées à des restrictions de bande passante. Vous pouvez définir des restrictions de bande passante et de session globales. Vous pouvez utiliser le Panneau de Skype Entreprise Server pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies. Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau. Effectuez les procédures suivantes pour créer ou modifier un profil de stratégie de bande passante. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>Pour créer un profil de stratégie de bande passante

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau,** puis sur Stratégie de bande **passante.**

4.  Dans la page **Stratégie de bande passante**, cliquez sur **Nouveau**.

5.  Dans **Nouveau profil de stratégie de bande passante**, tapez un nom dans le champ **Nom**. Ce nom doit être unique parmi tous les profils de stratégie de bande passante.

6.  Dans le champ **Limite audio**, tapez une valeur numérique. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour toutes les connexions audio.

7.  Entrez une valeur numérique dans le champ **Limite de session audio**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour une connexion audio. Cette valeur doit être égale ou supérieure à 40.

8.  Entrez une valeur numérique dans le champ **Limite vidéo**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour toutes les connexions vidéo.

9.  Entrez une valeur numérique dans le champ **Limite de session vidéo**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour une connexion vidéo. Cette valeur doit être égale ou supérieure à 100.

10. (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce profil de stratégie de bande passante, car son nom ne suffit pas à le décrire.

11. Cliquez sur **Valider**.

    > [!NOTE]  
    > La création d’un nouveau profil de stratégie de bande passante n’applique pas automatiquement les restrictions de bande passante. Vous devez d’abord associer le profil de stratégie à un site. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>Pour modifier un profil de stratégie de bande passante

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau,** puis sur Stratégie de bande **passante.**

4.  Dans la page **Stratégie de bande passante**, cliquez sur le profil de stratégie de bande passante que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier le profil de stratégie de** bande passante, modifiez les champs si nécessaire (pour plus d’informations, voir Pour créer un profil de stratégie de bande [passante).](#to-create-a-new-bandwidth-policy-profile)

7.  Cliquez sur **Valider**.

    > [!NOTE]  
    > Lorsque vous modifiez le profil de stratégie de bande passante, celui-ci met immédiatement à jour les restrictions de bande passante de tous les sites réseau qui lui sont associés.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Supprimer les profils de stratégie de bande passante réseau

La stratégie de bande passante utilisée dans le cadre du contrôle d’admission des appels (CAC) permet de définir des restrictions de bande passante pour des modes bien précis. Dans Skype Entreprise Server, seules les modalités audio et vidéo peuvent être affectées à des restrictions de bande passante. Vous pouvez définir des restrictions de bande passante et de session globales. Vous pouvez utiliser le Panneau de Skype Entreprise Server pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies. Utilisez les procédures suivantes pour supprimer des profils de stratégies de bande passante réseau. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>Pour supprimer un profil de stratégie de bande passante

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau,** puis sur Stratégie de bande **passante.**

4.  Dans la page **Stratégie de bande passante**, cliquez sur le profil de stratégie de bande passante que vous souhaitez supprimer.

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs profils à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs profils. Pour sélectionner tous les profils, cliquez sur **Sélectionner tout** dans le menu **Edition**.

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.
   

    > [!WARNING]  
    > Vous ne pouvez pas supprimer un profil de stratégie de bande passante associé à un site réseau. Vous devez d’abord supprimer l’association au site réseau avant de supprimer le profil. 


## <a name="see-also"></a>Voir aussi

[Gestion du contrôle d’admission des appels pour les sites](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
