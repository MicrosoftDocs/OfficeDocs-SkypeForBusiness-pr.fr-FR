---
title: Gestion du contrôle d’admission des appels pour les sites
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Les sites réseau sont les bureaux ou emplacements au sein de chaque région réseau des déploiements du service Contrôle d’admission des appels, du service E9-1-1 ou du contournement de médias.
ms.openlocfilehash: 114c8687de3273e09f4cc4ef122a0c584f97237e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745960"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Gestion du contrôle d’admission des appels pour les sites dans Skype Entreprise Server

Les sites réseau sont les bureaux ou emplacements au sein de chaque région réseau des déploiements du service Contrôle d’admission des appels, du service E9-1-1 ou du contournement de médias. Utilisez les procédures de cet article pour configurer le contrôle d’admission des appels pour les sites réseau.

## <a name="configure-network-site-links"></a>Configurer des liens de sites réseau

Dans une configuration de contrôle d’admission des appels (CAC), vous pouvez créer des stratégies réseau intersessant qui définissent des limites de bande passante entre les sites qui sont directement liés. Quand des sites de réseau partagent un lien direct, des restrictions de bande passante pour les connexions audio et vidéo peuvent être définies pour lesdits sites. Vous ne pouvez pas utiliser le Panneau de configuration Skype Entreprise Server pour configurer des stratégies de site réseau. Pour ce faire, vous pouvez uniquement utiliser les cmdlets de Skype Entreprise Server Management Shell. Vous pouvez créer, modifier et supprimer un lien de site réseau (également appelé stratégie intersessant réseau) à partir de Skype Entreprise Server Management Shell.

### <a name="to-create-a-network-site-link"></a>Pour créer un lien de site réseau

1.  Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires.

2.  Démarrez l Skype Entreprise Server Management Shell : cliquez sur Démarrer, sur Tous les **programmes,** sur **Skype Entreprise Server,** puis sur Skype Entreprise Server **Management Shell.**

3.  À l’invite de commandes, tapez la commande suivante en spécifiant les valeurs valides pour votre configuration :
    
     **New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits**
    
    Cet exemple crée un lien de site réseau nommé Reno Portland qui définit des limites de bande passante entre les sites réseau \_ Reno et Portland. Les sites réseau et le profil de stratégie de bande passante doivent être existants avant d’exécuter cette commande.

Pour obtenir des descriptions détaillées des paramètres, voir [New-CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy). Pour récupérer une liste des profils de stratégie de bande passante pouvant être appliqués au lien de site réseau, appelez l’applet de commande **Get-CsNetworkBandwidthPolicyProfile**. Pour plus d’informations, [voir Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

### <a name="to-modify-a-network-site-link"></a>Pour modifier un lien de site réseau

1.  Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires.

2.  Démarrez l Skype Entreprise Server Management Shell : cliquez sur Démarrer, sur Tous les **programmes,** sur **Skype Entreprise Server,** puis sur Skype Entreprise Server **Management Shell.**

3.  Utilisez l’applet de commande **Set-CsNetworkInterSitePolicy** pour modifier les propriétés d’un lien de site réseau donné. Vous pouvez modifier l’un ou l’autre des sites connectés, ou les deux, ainsi que le profil de stratégie de bande passante associé au lien. Voici un exemple de modification du profil de stratégie de bande passante d’un lien de site nommé Reno \_ Portland :
    
    **Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits**

Pour obtenir des descriptions détaillées des paramètres, voir [Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy).


### <a name="to-delete-a-network-site-link"></a>Pour supprimer un lien de site réseau

1.  Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires.

2.  Démarrez l Skype Entreprise Server Management Shell : cliquez sur Démarrer, sur Tous les **programmes,** sur **Skype Entreprise Server,** puis sur Skype Entreprise Server **Management Shell.**

3.  Utilisez l’applet de commande **Remove-CsNetworkInterSitePolicy** pour supprimer un lien de site réseau. L’exemple suivant supprime le lien de site réseau Reno \_ Portland :
    
    **Remove-CsNetworkInterSitePolicy -Identity Reno_Portland**

Pour obtenir des descriptions détaillées des paramètres, voir [Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy).


## <a name="view-network-site-information"></a>Afficher les informations du site réseau

Les sites réseau sont les bureaux ou emplacements configurés au sein de chaque région d’un contrôle d’admission des appels (Call Admission Control ou CAC) ou encore d’un déploiement Enhanced 9-1-1. Vous pouvez afficher les informations de site réseau dans le Panneau de Skype Entreprise Server ou l’Skype Entreprise Server Management Shell. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Pour afficher les informations de site réseau dans le Skype Entreprise Server de contrôle

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Site.**

4.  Dans la page **Site**, cliquez sur le site que vous souhaitez afficher.
 
    > [!NOTE]
    > Vous ne pouvez afficher les informations que d’un site à la fois.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de site réseau à l’aide Windows PowerShell cmdlets

Vous pouvez afficher les informations de site réseau à l’Windows PowerShell et à l'Get-CsNetworkSite cmdlet. Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 

### <a name="to-view-network-site-information"></a>Pour afficher des informations sur les sites réseau

  - Pour afficher des informations sur tous vos sites réseau, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
    **Get-CsNetworkSite**
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
    Identité : Redmond<br/>
    NetworkSiteID : Redmond<br/>
    Description :<br/>
    NetworkRegionID : Nord-Ouest pacifique<br/>
    BypassID : 3b232b84-2c1d-4da2-8181-e9330bafebe9<br/>
    BWPolicyProfileID :<br/>
    LocationPolicy :<br/>

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite).


## <a name="create-or-modify-network-sites"></a>Créer ou modifier des sites réseau 

Les sites réseau sont les bureaux ou emplacements configurés au sein de chaque région d’un contrôle d’admission des appels (Call Admission Control ou CAC) ou encore d’un déploiement Enhanced 9-1-1. Vous pouvez utiliser le Panneau de configuration Skype Entreprise Server pour configurer des sites et les associer à des régions. Par exemple, vous pouvez associer la région réseau Amérique du Nord à des sites réseau, tels que Chicago, Redmond et Vancouver. Un site réseau CAC doit être créé pour chaque site dans l’organisation, même en l’absence de limitation de bande passante pour ce site. À partir Skype Entreprise Server panneau de bord, vous pouvez créer, modifier et supprimer des sites réseau. Utilisez les procédures suivantes pour créer ou modifier un site réseau. 

### <a name="to-create-a-network-site"></a>Pour créer un site réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Site.**

4.  Dans la page **Site**, cliquez sur **Nouveau**.

5.  Dans **Nouveau site**, renseignez le champ **Nom**.

    > [!NOTE]  
    > Les noms de site doivent être uniques dans le déploiement Skype Entreprise Server de sites.

6.  Dans la liste déroulante **Région**, sélectionnez une région réseau à associer au site.

7.  (Facultatif) Si vous voulez imposer sur ce site des limitations de bande passante aux appels audio ou vidéo, sélectionnez le profil de stratégie de bande passante adéquat dans la liste déroulante **Stratégie de bande passante**.
 
    > [!NOTE]  
    > Vous pouvez afficher les détails des profils de stratégie de bande passante disponibles ou créer un profil de stratégie de bande passante dans la page **Profil** de stratégie du **groupe Configuration** du réseau. Pour plus d’informations, voir [Gestion des profils de stratégie de bande passante réseau.](managing-network-bandwidth-policy-profiles.md)

8.  (Facultatif) Si vous voulez spécifier des paramètres d’emplacement pour ce site, sélectionnez une stratégie d’emplacement dans la liste déroulante **Stratégie d’emplacement**.

    > [!NOTE]  
    > La stratégie d’emplacement affecte les paramètres Enhanced 9-1-1 (E9-1-1) et d’emplacement des clients au site. Vous pouvez afficher les détails des stratégies d’emplacement ou créer une stratégie d’emplacement dans la page **Stratégie d’emplacement** du groupe **Configuration du réseau**. 

9.  (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce site, car son nom ne suffit pas à le décrire.

10. Cliquez sur **Valider**.

    > [!NOTE]  
    > Lors de la création d’un site réseau, vous n’utilisez pas la table **Sous-réseaux associés**. Vous associez un sous-réseau à un site lorsque vous créez ou modifiez le sous-réseau. Pour plus d’informations, voir [Gestion des sous-réseaux.](managing-network-subnets.md)

### <a name="to-modify-a-network-site"></a>Pour modifier un site réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Site.**

4.  Dans la page **Site**, cliquez sur le site que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier le site**, vous pouvez modifier la description, la région, le profil de la stratégie de bande passante et la stratégie d’emplacement associés au site. Pour plus d’informations, voir [Pour créer un site réseau ci-dessus.](#to-create-a-network-site)

7.  Cliquez sur **Valider**.

Vous ne pouvez pas modifier la table **Sous-réseaux associés** de cette page. La liste de sous-réseaux associés est donnée à titre de référence de sorte que vous sachiez quels sous-réseaux seront affectés par les paramètres que vous modifiez.


## <a name="delete-an-existing-network-site"></a>Supprimer un site réseau existant

Les sites réseau sont les bureaux ou emplacements configurés au sein de chaque région d’un contrôle d’admission des appels (Call Admission Control ou CAC) ou encore d’un déploiement Enhanced 9-1-1. Vous pouvez utiliser le Panneau de configuration Skype Entreprise Server pour configurer des sites et les associer à des régions. Par exemple, vous pouvez associer la région réseau Amérique du Nord à des sites réseau, tels que Chicago, Redmond et Vancouver. Un site réseau CAC doit être créé pour chaque site dans l’organisation, même en l’absence de limitation de bande passante pour ce site. À partir Skype Entreprise Server panneau de bord, vous pouvez créer, modifier et supprimer des sites réseau. Utilisez la procédure suivante pour supprimer un site réseau existant. Pour plus d’informations sur la création ou la modification de sites réseau, voir Gestion du contrôle [d’admission des appels pour les sites.](managing-call-admission-control-for-sites.md)


### <a name="to-delete-a-network-site"></a>Pour supprimer un site réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Site.**

4.  Dans la page **Site**, cliquez sur le site que vous souhaitez supprimer.

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs sites à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs sites. Ou, pour sélectionner tous les sites, cliquez sur **Sélectionner tout** dans le menu **Edition**.

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.
    

    > [!WARNING]  
    > Vous ne pouvez pas supprimer un site réseau associé à un sous-réseau de réseau. Si vous essayez, vous recevrez un message d’erreur. Pour savoir si un site est associé à des sous-réseaux, cliquez sur le site, puis sur **Afficher les détails** dans le menu **Edition**.


## <a name="see-also"></a>Voir aussi


[New-CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite)