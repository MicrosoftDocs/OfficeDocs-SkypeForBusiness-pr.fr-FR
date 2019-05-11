---
title: Liaison des régions réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Vous pouvez configurer des liens entre deux régions de réseau dans le cadre du contrôle d’admission des appels (CAC). '
ms.openlocfilehash: 30d4a020826b24c3615ce059809645481466efc3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888351"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Liaison des régions réseau dans Skype Entreprise Server

Vous pouvez configurer des liens entre deux régions de réseau dans le cadre du contrôle d’admission des appels (CAC). Utilisez les sections de cet article pour afficher les informations de lien de région PERIPHERIE, configurer ou supprimer des liens de région réseau. 

## <a name="view-network-region-link-information"></a>Affichage des informations de lien de région de réseau 

Vous pouvez afficher les liens entre deux régions de réseau dans le cadre du contrôle d’admission des appels (CAC). Régions au sein d’un réseau sont liées par le biais de connectivité de réseau (étendu WAN) étendu physique. Vous pouvez utiliser la Skype pour Business Server Control Panel pour afficher un lien entre deux régions de réseau. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Pour afficher un lien de région réseau dans Skype pour Business Server Control Panel

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **Lien de région**.

4.  Dans la page **Lien de région** , cliquez sur le lien de région que vous souhaitez afficher.
    
    > [!NOTE]  
    > Vous ne pouvez afficher des informations sur un lien de région à la fois.

5.  Dans le menu **Edition** , sélectionnez **Afficher les détails**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Afficher les informations de lien de région réseau à l’aide des applets de commande Windows PowerShell

Vous pouvez afficher les liens de région réseau à l’aide de Windows PowerShell et l’applet de commande **Get-CsNetworkRegionLink** . Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. 


### <a name="to-view-network-region-link-information"></a>Pour afficher les informations de lien de région réseau

  - Pour afficher des informations sur tous les liens de région réseau, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :
    
        Get-CsNetworkRegionLink
    
    Cette commande renvoie le type d’informations suivant :
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


Pour plus d’informations, voir [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Configurer les liens de région réseau 

Vous pouvez configurer des liens entre deux régions de réseau dans le cadre du contrôle d’admission des appels (CAC). Régions au sein d’un réseau sont liées par le biais de connectivité de réseau (étendu WAN) étendu physique. Vous pouvez utiliser la Skype pour Business Server Control Panel pour définir un lien entre deux régions de réseau et les limitations de bande passante sur les connexions audio et vidéo entre ces régions.

### <a name="to-create-a-network-region-link"></a>Pour créer un lien de région réseau

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **Lien de région**.

4.  Dans la page **Lien de région** , cliquez sur **Nouveau**.

5.  Dans le **Nouveau lien de région**, tapez une valeur dans le champ **nom** .
 
    > [!NOTE]  
    > Cette valeur doit être unique au sein de votre Skype pour le déploiement de serveur d’entreprise.

6.  À partir de la **région réseau \#1** liste déroulante, sélectionnez une des deux régions à lier.

7.  À partir de la **région réseau \#2** liste déroulante, sélectionnez l’autre région à lier. Cette zone doit être différente de la région sélectionnée pour la région de réseau \#1.

8.  (Facultatif) Si vous souhaitez placer des restrictions de bande passante pour les appels audio ou vidéos entre ces régions, sélectionnez un profil de stratégie de bande passante dans la liste déroulante **stratégie de bande passante** .

9.  Cliquez sur **Valider**.

### <a name="to-modify-a-network-region-link"></a>Pour modifier un lien de région réseau

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **Lien de région**.

4.  Dans la page **Lien de région** , cliquez sur le lien de région que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans **Modifier un lien de région**, vous pouvez modifier les régions liées ou le profil de stratégie de bande passante pour ce lien.

7.  Cliquez sur **Valider**.


## <a name="delete-network-region-links"></a>Supprimer les liens de région réseau

Vous pouvez configurer des liens entre deux régions de réseau dans le cadre du contrôle d’admission des appels (CAC). Régions au sein d’un réseau sont liées par le biais de connectivité de réseau (étendu WAN) étendu physique. Vous pouvez utiliser la Skype pour Business Server Control Panel pour supprimer un lien entre deux régions de réseau. 

### <a name="to-delete-a-network-region-link"></a>Pour supprimer un lien de région réseau

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **Lien de région**.

4.  Dans la page **Lien de région** , cliquez sur le lien de région que vous souhaitez supprimer.
 
    > [!NOTE]  
    > Vous pouvez supprimer plus d’un lien de région à la fois. Pour ce faire, appuyez sur la touche CTRL ENFONCÉE et sélectionnez plusieurs liens de région tout en maintenant la touche CTRL enfoncée. Ou, pour sélectionner tous les liens de région, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG> .

5.  Dans le menu **Edition** , sélectionnez **Supprimer**.

6.  Cliquez sur **OK**.


## <a name="see-also"></a>Voir aussi

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
