---
title: Gestion du contrôle d’admission des appels pour les sites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Les sites réseau sont les bureaux ou les emplacements dans chaque région du réseau de déploiement d’admission des appels (CAC), de E9-1-1 et de contournement de média.
ms.openlocfilehash: a90781eae38d92d560dd1bf34db3b6918e8aeaf5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279542"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Gestion du contrôle d’admission des appels pour les sites dans Skype Entreprise Server

Les sites réseau sont les bureaux ou les emplacements dans chaque région du réseau de déploiement d’admission des appels (CAC), de E9-1-1 et de contournement de média. Suivez les procédures décrites dans cet article pour configurer le contrôle d’admission des appels pour les sites réseau.

## <a name="configure-network-site-links"></a>Configurer les liens du site réseau

Dans le cadre d’une configuration de contrôle d’admission des appels (CAC), vous pouvez créer des stratégies entre site réseau qui définissent les limitations de bande passante entre les sites qui sont directement liés. Lorsque les sites réseau partagent un lien direct, les limites de bande passante pour les connexions audio et vidéo peuvent être définies entre ces deux sites. Vous ne pouvez pas utiliser le panneau de configuration Skype entreprise Server pour configurer des stratégies de site réseau, et ce n’est possible qu’en utilisant des applets de commande de Skype entreprise Server Management Shell. Vous pouvez créer, modifier et supprimer un lien de site réseau (également connu sous le nom de stratégie intersite réseau) dans Skype entreprise Server Management Shell.

### <a name="to-create-a-network-site-link"></a>Pour créer un lien de site réseau

1.  Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires.

2.  Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise Server**, puis cliquez sur **Skype entreprise Server Management Shell**.

3.  À partir de l’invite de commandes, tapez la commande suivante, en remplaçant les valeurs valides pour votre configuration:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Cet exemple crée un lien de site réseau intitulé Reno\_Portland qui définit les limites de bande passante entre les sites réseau Reno et Portland. Les sites réseau et le profil de la stratégie de bande passante doivent déjà exister avant d’exécuter cette commande.

Pour obtenir une description détaillée des paramètres, consultez la rubrique [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy). Pour récupérer la liste des profils de stratégie de bande passante qui peuvent être appliqués au lien site réseau, appelez l’applet **de passe Get-CsNetworkBandwidthPolicyProfile** . Pour plus d’informations, consultez la rubrique [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

### <a name="to-modify-a-network-site-link"></a>Pour modifier un lien de site réseau

1.  Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires.

2.  Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise Server**, puis cliquez sur **Skype entreprise Server Management Shell**.

3.  Utilisez l’applet de connexion **Set-CsNetworkInterSitePolicy** pour modifier les propriétés d’un lien de site réseau donné. Vous pouvez modifier l’un ou l’autre des sites connectés, et vous pouvez modifier le profil de la stratégie de bande passante associé au lien. Voici un exemple de modification du profil de la stratégie de bande passante d’un lien\_de site nommé Reno Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Pour obtenir une description détaillée des paramètres, consultez la rubrique [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).


### <a name="to-delete-a-network-site-link"></a>Pour supprimer un lien de site réseau

1.  Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires.

2.  Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise Server**, puis cliquez sur **Skype entreprise Server Management Shell**.

3.  Utilisez l’applet de connexion **Remove-CsNetworkInterSitePolicy** pour supprimer un lien de site réseau. Dans l’exemple suivant, le lien\_vers le site réseau de Portland de Reno est supprimé:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Pour obtenir une description détaillée des paramètres, consultez la rubrique [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).


## <a name="view-network-site-information"></a>Afficher les informations relatives au site réseau

Les sites réseau sont les bureaux ou les emplacements configurés dans chaque région d’un contrôle d’admission des appels (CAC) ou un déploiement 9-1-1 amélioré. Vous pouvez afficher les informations relatives à un site réseau dans le panneau de configuration Skype entreprise Server ou dans Skype entreprise Server Management Shell. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Pour afficher les informations sur le site réseau dans Skype entreprise Server panneau de configuration

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **site**.

4.  Sur la page du **site** , cliquez sur le site que vous voulez afficher.
 
    > [!NOTE]  
    > Vous ne pouvez afficher que les informations relatives à un site à la fois.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations sur le site réseau à l’aide des cmdlets Windows PowerShell

Vous pouvez afficher les informations de site réseau en utilisant Windows PowerShell et l’applet de connexion Get-CsNetworkSite. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 

### <a name="to-view-network-site-information"></a>Pour afficher les informations relatives au site réseau

  - Pour afficher des informations sur tous les sites de votre réseau, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée:
    
        Get-CsNetworkSite
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .


## <a name="create-or-modify-network-sites"></a>Créer ou modifier des sites réseau 

Les sites réseau sont les bureaux ou les emplacements configurés dans chaque région d’un contrôle d’admission des appels (CAC) ou un déploiement 9-1-1 amélioré. Vous pouvez utiliser le panneau de configuration Skype entreprise Server pour configurer les sites et les associer à des régions. Par exemple, une région réseau pour l’Amérique du Nord peut être associée à des sites réseaux tels que Chicago, Redmond et Vancouver. Un site réseau CAC doit être créé pour chaque site au sein d’une organisation, même si ce site n’a pas de limitations de bande passante. Le panneau de configuration Skype entreprise Server vous permet de créer, de modifier et de supprimer des sites réseau. Pour créer ou modifier un site réseau, procédez comme suit. 

### <a name="to-create-a-network-site"></a>Pour créer un site réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **site**.

4.  Sur la page du **site** , cliquez sur **nouveau**.

5.  Dans **nouveau site**, tapez un nom pour ce site dans le champ **nom** .

    > [!NOTE]  
    > Les noms de site doivent être uniques dans le déploiement de Skype entreprise Server.

6.  Dans la liste déroulante **région** , sélectionnez une région réseau à associer à ce site.

7.  Facultatif Si vous voulez appliquer des limitations de bande passante pour les appels audio ou vidéo vers ce site, sélectionnez le profil de la stratégie de bande passante avec les paramètres appropriés dans la liste déroulante **stratégie de bande passante** .
 
    > [!NOTE]  
    > Vous pouvez afficher les détails des profils de stratégie de bande passante disponibles ou créer un nouveau profil de stratégie de bande passante dans la page profil de la **stratégie** du groupe de **Configuration réseau** . Pour plus d’informations, consultez [gestion des profils de stratégie de bande passante réseau](managing-network-bandwidth-policy-profiles.md).

8.  Facultatif Si vous voulez fournir des paramètres d’emplacement pour ce site, sélectionnez une stratégie d’emplacement dans la liste déroulante **stratégie d’emplacement** .

    > [!NOTE]  
    > La stratégie d’emplacement attribue des paramètres de 9-1-1 et d’emplacement client spécifiques au site. Vous pouvez afficher les détails des stratégies d’emplacement disponibles ou créer une nouvelle stratégie d’emplacement à partir de la page **stratégie d’emplacement** du groupe de **Configuration réseau** . 

9.  Facultatif Tapez une valeur dans le champ **Description** pour fournir des informations supplémentaires sur ce site qui ne peut pas être exprimé uniquement par le nom.

10. Cliquez sur **Valider**.

    > [!NOTE]  
    > Vous n’utilisez pas la table de **sous-réseaux associés** lorsque vous créez un site réseau. Vous associez un sous-réseau à un site lors de la création ou de la modification du sous-réseau. Pour plus d’informations, reportez-vous à [gestion des sous-réseaux réseau](managing-network-subnets.md).

### <a name="to-modify-a-network-site"></a>Pour modifier un site réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **site**.

4.  Sur la page du **site** , cliquez sur le site que vous voulez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **modifier le site** , vous pouvez modifier la description, la région, le profil de la stratégie de bande passante et la stratégie d’emplacement associées au site. Pour plus d’informations, reportez-vous [à créer un site réseau](#to-create-a-network-site) ci-dessus.

7.  Cliquez sur **Valider**.

Vous ne pouvez pas modifier le tableau sous- **réseaux associés** sur cette page. La liste des sous-réseaux associés est fournie à des fins de référence afin de savoir quels sous-réseaux seront affectés lorsque vous modifiez les paramètres du site.


## <a name="delete-an-existing-network-site"></a>Supprimer un site réseau existant

Les sites réseau sont les bureaux ou les emplacements configurés dans chaque région d’un contrôle d’admission des appels (CAC) ou un déploiement 9-1-1 amélioré. Vous pouvez utiliser le panneau de configuration Skype entreprise Server pour configurer les sites et les associer à des régions. Par exemple, une région réseau pour l’Amérique du Nord peut être associée à des sites réseaux tels que Chicago, Redmond et Vancouver. Un site réseau CAC doit être créé pour chaque site au sein d’une organisation, même si ce site n’a pas de limitations de bande passante. Le panneau de configuration Skype entreprise Server vous permet de créer, de modifier et de supprimer des sites réseau. Utilisez la procédure suivante pour supprimer un site réseau existant. Pour plus d’informations sur la création ou la modification de sites réseau, voir [gestion du contrôle d’admission des appels pour les sites](managing-call-admission-control-for-sites.md).


### <a name="to-delete-a-network-site"></a>Pour supprimer un site réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **site**.

4.  Sur la page du **site** , cliquez sur le site que vous voulez supprimer.

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs sites à la fois. Pour cela, appuyez sur CTRL et sélectionnez plusieurs sites tout en maintenant la touche CTRL enfoncée. Pour sélectionner tous les sites, dans le menu **Edition** , cliquez sur **Sélectionner tout** .

5.  Dans le menu **modifier** , cliquez sur **supprimer**.

6.  Cliquez sur **OK**.
    

    > [!WARNING]  
    > Vous ne pouvez pas supprimer un site réseau s’il est associé à un sous-réseau. Si vous tentez de supprimer un site associé à un sous-réseau, vous recevez un message d’erreur. Pour savoir si un site est associé à des sous-réseaux, cliquez sur le site, puis cliquez sur **afficher les détails** dans le menu **modifier** .


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
