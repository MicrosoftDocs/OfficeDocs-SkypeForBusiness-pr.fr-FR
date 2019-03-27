---
title: Gérer le contrôle d’admission des appels pour les sites d’appel
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sites de réseau sont les bureaux ou emplacements dans chaque région réseau de contrôle d’admission des appels (CAC), E9-1-1 et les déploiements de contournement de média d’appel.
ms.openlocfilehash: 53140cf03110991f2c757e5d52e30a6c7db1d7de
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895418"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Gestion du contrôle d’admission des appels pour les sites dans Skype Entreprise Server

Sites de réseau sont les bureaux ou emplacements dans chaque région réseau de contrôle d’admission des appels (CAC), E9-1-1 et les déploiements de contournement de média d’appel. Utilisez les procédures décrites dans cet article pour configurer le contrôle d’admission des appels d’appel pour les sites réseau.

## <a name="configure-network-site-links"></a>Configurer les liens de site réseau

Dans une configuration de contrôle (CAC) d’admission des appels, vous pouvez créer des stratégies inter-sites qui définissent les limitations de bande passante entre les sites qui sont directement liés réseau. Lorsque les sites de réseau partagent un lien direct, des restrictions de bande passante pour les connexions audio et vidéos peuvent être définies entre ces deux sites. Vous ne pouvez pas utiliser le Skype pour Business Server Control Panel pour configurer les stratégies de site réseau, cette opération peut être effectuée uniquement à l’aide des applets de commande de le Skype pour Business Server Management Shell. Vous pouvez créer, modifier et supprimer un lien de site réseau (également appelé une stratégie intersite réseau) de la Skype pour Business Server Management Shell.

### <a name="to-create-a-network-site-link"></a>Pour créer un lien de site réseau

1.  Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires.

2.  Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour Business Server Management Shell**.

3.  À partir de l’invite de commandes, tapez la commande suivante, en remplaçant les valeurs valides pour votre configuration :
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Cet exemple crée un nouveau lien de site réseau appelé Reno\_Portland qui définit les restrictions de bande passante entre les sites de réseau Reno et Portland. Les sites réseau et le profil de stratégie de bande passante doivent déjà exister avant d’exécuter cette commande.

Pour obtenir des descriptions détaillées de paramètre, voir [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy). Pour récupérer une liste de profils de stratégie de bande passante qui peuvent être appliqués à la liaison de site réseau, appelez l’applet de commande **Get-CsNetworkBandwidthPolicyProfile** . Pour plus d’informations, voir [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

### <a name="to-modify-a-network-site-link"></a>Pour modifier un lien de site réseau

1.  Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires.

2.  Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour Business Server Management Shell**.

3.  Utilisez l’applet de commande **Set-CsNetworkInterSitePolicy** pour modifier les propriétés d’un lien de site réseau donné. Vous pouvez modifier un (ou les deux) ou les sites connectés et vous pouvez modifier le profil de stratégie de bande passante associé au lien. Voici un exemple de modification du profil de stratégie de bande passante d’un lien de site nommé Reno\_Portland :
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Pour obtenir des descriptions détaillées de paramètre, voir [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).


### <a name="to-delete-a-network-site-link"></a>Pour supprimer un lien de site réseau

1.  Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires.

2.  Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour Business Server Management Shell**.

3.  Utilisez l’applet de commande **Remove-CsNetworkInterSitePolicy** pour supprimer un lien de site réseau. L’exemple suivant supprime le Reno\_lien de site réseau Portland :
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Pour obtenir des descriptions détaillées de paramètre, voir [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).


## <a name="view-network-site-information"></a>Afficher les informations de site réseau

Sites de réseau sont les bureaux et emplacements configurés au sein de chaque région du déploiement d’une le contrôle d’admission des appels (CAC) ou Enhanced 9-1-1. Vous pouvez afficher des informations de site réseau dans le deux Skype pour le panneau de configuration serveur Business ou le Skype pour Business Server Management Shell. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Pour afficher les informations de site réseau dans Skype pour Business Server Control Panel

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **sites**.

4.  Dans la page du **Site** , cliquez sur le site que vous souhaitez afficher.
 
    > [!NOTE]  
    > Vous ne pouvez afficher des informations pour un site à la fois.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de site réseau à l’aide des applets de commande Windows PowerShell

Vous pouvez afficher les informations de site réseau à l’aide de Windows PowerShell et l’applet de commande Get-CsNetworkSite. Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. 

### <a name="to-view-network-site-information"></a>Pour afficher les informations de site réseau

  - Pour afficher des informations sur tous les sites de votre réseau, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :
    
        Get-CsNetworkSite
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .


## <a name="create-or-modify-network-sites"></a>Créer ou modifier des sites réseau 

Sites de réseau sont les bureaux et emplacements configurés au sein de chaque région du déploiement d’une le contrôle d’admission des appels (CAC) ou Enhanced 9-1-1. Vous pouvez utiliser la Skype pour Business Server Control Panel pour configurer des sites et les associer à des régions. Par exemple, une région de réseau pour l’Amérique du Nord peut être associée à des sites de réseaux tels que Chicago, Redmond et Vancouver. Un site réseau CAC doit être créé pour chaque site au sein d’une organisation, même si ce site n’a aucune limitation de bande passante. À partir de la Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier et supprimer les sites de réseau. Utilisez les procédures suivantes pour créer ou modifier un site réseau. 

### <a name="to-create-a-network-site"></a>Pour créer un site réseau

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **sites**.

4.  Dans la page du **Site** , cliquez sur **Nouveau**.

5.  Dans le **Nouveau Site**, tapez un nom pour ce site dans le champ **nom** .

    > [!NOTE]  
    > Les noms de site doivent être uniques dans le Skype pour le déploiement de serveur d’entreprise.

6.  Dans la liste déroulante **région** , sélectionnez une région réseau à associer à ce site.

7.  (Facultatif) Si vous souhaitez placer des restrictions de bande passante pour les appels audio ou vidéos à ce site, sélectionnez le profil de stratégie de bande passante avec les paramètres appropriés à partir de la liste déroulante **stratégie de bande passante** .
 
    > [!NOTE]  
    > Vous pouvez afficher les détails des profils de stratégie de bande passante disponible, ou créer un nouveau profil de stratégie de bande passante, sur la page **Profil de stratégie** de groupe de la **Configuration réseau** . Pour plus d’informations, voir [profils de stratégie de bande passante réseau Managing](managing-network-bandwidth-policy-profiles.md).

8.  (Facultatif) Si vous souhaitez fournir des paramètres d’emplacement pour ce site, sélectionnez une stratégie d’emplacement dans la liste déroulante **stratégie d’emplacement** .

    > [!NOTE]  
    > La stratégie d’emplacement affecte spécifique Enhanced 9-1-1 (E9-1-1) et client paramètres d’emplacement pour le site. Vous pouvez afficher les détails de stratégies d’emplacement disponibles, ou créer une nouvelle stratégie d’emplacement, à partir de la page **Stratégie d’emplacement** du groupe **Configuration réseau** . 

9.  (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce site ne suffit pas au nom seul.

10. Cliquez sur **Valider**.

    > [!NOTE]  
    > Vous n’utilisez pas la table de **Sous-réseaux associés** lorsque vous créez un nouveau site réseau. Vous associez un sous-réseau à un site lorsque vous créez ou modifiez le sous-réseau. Pour plus d’informations, voir [Gestion des sous-réseaux](managing-network-subnets.md).

### <a name="to-modify-a-network-site"></a>Pour modifier un site réseau

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **sites**.

4.  Dans la page du **Site** , cliquez sur le site que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier le Site** , vous pouvez modifier la description, la région, profil de stratégie de bande passante et stratégie d’emplacement associés au site. Pour plus d’informations, voir [créer un site réseau](#to-create-a-network-site) ci-dessus.

7.  Cliquez sur **Valider**.

Vous ne pouvez pas modifier la table de **Sous-réseaux associés** sur cette page. La liste des sous-réseaux associés est fournie pour référence afin que vous connaissez les sous-réseaux seront affectés lorsque vous modifiez les paramètres du site.


## <a name="delete-an-existing-network-site"></a>Supprimer un site réseau existant

Sites de réseau sont les bureaux et emplacements configurés au sein de chaque région du déploiement d’une le contrôle d’admission des appels (CAC) ou Enhanced 9-1-1. Vous pouvez utiliser la Skype pour Business Server Control Panel pour configurer des sites et les associer à des régions. Par exemple, une région de réseau pour l’Amérique du Nord peut être associée à des sites de réseaux tels que Chicago, Redmond et Vancouver. Un site réseau CAC doit être créé pour chaque site au sein d’une organisation, même si ce site n’a aucune limitation de bande passante. À partir de la Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier et supprimer les sites de réseau. Utilisez la procédure suivante pour supprimer un site réseau existant. Pour plus d’informations sur la création ou modification des sites réseau, voir [Managing le contrôle d’admission des appels d’appel pour les sites](managing-call-admission-control-for-sites.md).


### <a name="to-delete-a-network-site"></a>Pour supprimer un site réseau

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **sites**.

4.  Dans la page du **Site** , cliquez sur le site que vous souhaitez supprimer.

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs sites à la fois. Pour ce faire, appuyez sur la touche CTRL ENFONCÉE et sélectionnez plusieurs sites tout en maintenant la touche CTRL enfoncée. Ou, pour sélectionner tous les sites, cliquez sur **Sélectionner tout** dans le menu **Edition** .

5.  Dans le menu **Edition** , cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.
    

    > [!WARNING]  
    > Vous ne pouvez pas supprimer un site réseau si elle est associée à un sous-réseau de réseau. Si vous tentez de supprimer un site associé à un sous-réseau, vous recevrez un message d’erreur. Pour voir si un site est associé à des sous-réseaux, cliquez sur le site, puis cliquez sur **Afficher les détails** dans le menu **Edition** .


## <a name="see-also"></a>Voir aussi


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
