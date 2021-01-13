---
title: Liaison de régions réseau
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Vous pouvez configurer les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC). '
ms.openlocfilehash: 0a4f5c63b4470fbfe6d2677f0e9e6f52841f7ebb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816464"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Liaison des régions réseau dans Skype Entreprise Server

Vous pouvez configurer les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC). Utilisez les sections de cet article pour afficher les informations de lien de région de travail nouveau ou configurer ou supprimer des liens de région netwrok. 

## <a name="view-network-region-link-information"></a>Afficher les informations de lien de région réseau 

Vous pouvez afficher les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC). Au sein d’un réseau, les régions sont liées par une connectivité physique au réseau étendu (WAN). Vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server pour afficher un lien existant entre deux régions réseau. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Pour afficher un lien de région réseau dans le Panneau de contrôle Skype Entreprise Server

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau,** puis cliquez sur **Lien de région.**

4.  Dans la page **Lien de région**, cliquez sur le lien de région que vous souhaitez afficher.
    
    > [!NOTE]  
    > Vous ne pouvez afficher des informations que sur un lien de région à la fois.

5.  Dans le menu **Edition**, sélectionnez **Afficher les détails**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Afficher les informations de lien de région réseau à l’Windows PowerShell cmdlets

Vous pouvez afficher les liens de région réseau à l’Windows PowerShell et à l’aide de l’cmdlet **Get-CsNetworkRegionLink.** Vous pouvez exécuter cette applet de commande à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 


### <a name="to-view-network-region-link-information"></a>Pour afficher les informations d’un lien de région réseau

  - Pour afficher des informations sur tous vos liens de région réseau, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsNetworkRegionLink
    
    Cette commande renvoie des informations comme celles-ci :
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


Pour plus d’informations, voir [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Configurer des liens de région réseau 

Vous pouvez configurer les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC). Au sein d’un réseau, les régions sont liées par une connectivité physique au réseau étendu (WAN). Vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server pour définir un lien entre deux régions réseau et définir les limites de bande passante sur les connexions audio et vidéo entre ces régions.

### <a name="to-create-a-network-region-link"></a>Pour créer un lien de région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau,** puis cliquez sur **Lien de région.**

4.  Dans la page **Lien de région**, cliquez sur **Nouveau**.

5.  Dans **Nouveau lien de région**, tapez une valeur dans le champ **Nom**.
 
    > [!NOTE]  
    > Cette valeur doit être unique dans votre déploiement Skype Entreprise Server.

6.  Dans la liste de listes listes de la région Réseau **\# 1,** sélectionnez l’une des deux régions à l lié.

7.  Dans la liste de listes bas Région réseau **\# 2,** sélectionnez l’autre région à l lié. Cette région doit être différente de la région sélectionnée pour la région \# réseau 1.

8.  (Facultatif) Si vous souhaitez ajouter des limites de bande passante sur les appels audio ou vidéo entre ces régions, sélectionnez un profil de stratégie de bande passante dans la liste déroulante **Stratégie de bande passante**.

9.  Cliquez sur **Valider**.

### <a name="to-modify-a-network-region-link"></a>Pour modifier un lien de région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau,** puis cliquez sur **Lien de région.**

4.  Dans la page **Lien de région**, cliquez sur le lien de région que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans **Modifier le lien de région**, vous pouvez modifier les régions liées ou le profil de stratégie de bande passante pour ce lien.

7.  Cliquez sur **Valider**.


## <a name="delete-network-region-links"></a>Supprimer des liens de région réseau

Vous pouvez configurer les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC). Au sein d’un réseau, les régions sont liées par une connectivité physique au réseau étendu (WAN). Vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server pour supprimer un lien existant entre deux régions réseau. 

### <a name="to-delete-a-network-region-link"></a>Pour supprimer un lien de région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau,** puis cliquez sur **Lien de région.**

4.  Dans la page **Lien de région**, cliquez sur le lien de région que vous souhaitez supprimer.
 
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs liens de région à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs liens de région. Ou, pour sélectionner tous les liens de région, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.

5.  Dans le menu **Edition**, sélectionnez **Supprimer**.

6.  Cliquez sur **OK**.


## <a name="see-also"></a>Voir aussi

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
