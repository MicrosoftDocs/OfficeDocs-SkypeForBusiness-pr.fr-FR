---
title: Liaison des régions réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Vous pouvez configurer des liens entre deux régions réseau dans le cadre de la commande d’admission des appels (CAC). '
ms.openlocfilehash: 4a643f34b9525b53168b9015b77a7f8292abd417
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817523"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Liaison des régions réseau dans Skype Entreprise Server

Vous pouvez configurer des liens entre deux régions réseau dans le cadre de la commande d’admission des appels (CAC). Les sections de cet article vous permettent d’afficher des informations sur le lien de la région newtwork ou de configurer ou supprimer des liens vers des régions Netwrok. 

## <a name="view-network-region-link-information"></a>Afficher les informations sur le lien de la région de réseau 

Vous pouvez afficher les liens entre deux régions réseau dans le cadre du contrôle d’admission des appels (CAC). Les régions d’un réseau sont liées par le biais de la connectivité du réseau étendu (WAN) physique. Le panneau de configuration Skype entreprise Server vous permet d’afficher un lien existant entre deux régions du réseau. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Pour afficher un lien de région réseau dans le panneau de configuration Skype entreprise Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **liaison de région**.

4.  Dans la page de liaison de la **zone** , cliquez sur le lien de la région que vous souhaitez afficher.
    
    > [!NOTE]  
    > Vous pouvez uniquement afficher des informations sur un lien de région à la fois.

5.  Dans le menu **édition** , cliquez sur **afficher les détails**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Afficher les informations sur les liens de région réseau à l’aide d’applets de requête Windows PowerShell

Vous pouvez afficher les liens de région réseau à l’aide de Windows PowerShell et de l’applet **de requête get-CsNetworkRegionLink** . Vous pouvez exécuter cette applet de commande dans Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 


### <a name="to-view-network-region-link-information"></a>Pour afficher les informations sur le lien dans la région réseau

  - Pour afficher des informations sur tous les liens de votre région réseau, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :
    
        Get-CsNetworkRegionLink
    
    Cette commande renvoie le type d’informations suivant :
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


Pour plus d’informations, consultez la rubrique [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Configurer les liens de région réseau 

Vous pouvez configurer des liens entre deux régions réseau dans le cadre de la commande d’admission des appels (CAC). Les régions d’un réseau sont liées par le biais de la connectivité du réseau étendu (WAN) physique. Le panneau de configuration Skype entreprise Server vous permet de définir un lien entre deux régions du réseau et de définir les limites de bande passante pour les connexions audio et vidéo entre ces régions.

### <a name="to-create-a-network-region-link"></a>Pour créer un lien de région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **liaison de région**.

4.  Dans la page de **liaison région** , cliquez sur **nouveau**.

5.  Dans le **lien nouvelle zone**, tapez une valeur dans le champ **nom** .
 
    > [!NOTE]  
    > Cette valeur doit être unique dans le cadre de votre déploiement Skype entreprise Server.

6.  Dans la liste déroulante ** \#région réseau 1** , sélectionnez l’une des deux régions à lier.

7.  Dans la liste déroulante ** \#région de réseau 2** , sélectionnez la autre zone à lier. Cette région doit être différente de la région sélectionnée pour la région \#réseau 1.

8.  Facultatif Si vous voulez appliquer des limitations de bande passante aux appels audio et vidéo entre ces régions, sélectionnez un profil de stratégie de bande passante dans la liste déroulante **stratégie de bande passante** .

9.  Cliquez sur **Valider**.

### <a name="to-modify-a-network-region-link"></a>Pour modifier un lien de région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **liaison de région**.

4.  Dans la page de liaison de la **zone** , cliquez sur le lien dans la région que vous voulez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans le **lien modifier la région**, vous pouvez modifier les régions liées ou le profil de la stratégie de bande passante pour ce lien.

7.  Cliquez sur **Valider**.


## <a name="delete-network-region-links"></a>Supprimer des liens de région réseau

Vous pouvez configurer des liens entre deux régions réseau dans le cadre de la commande d’admission des appels (CAC). Les régions d’un réseau sont liées par le biais de la connectivité du réseau étendu (WAN) physique. Le panneau de configuration Skype entreprise Server vous permet de supprimer un lien existant entre deux régions du réseau. 

### <a name="to-delete-a-network-region-link"></a>Pour supprimer un lien de zone réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **liaison de région**.

4.  Dans la page de liaison de la **zone** , cliquez sur le lien dans la région que vous voulez supprimer.
 
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs liens vers une région à la fois. Pour cela, appuyez sur CTRL et sélectionnez les liens de plusieurs régions tout en maintenant la touche CTRL enfoncée. Pour sélectionner tous les liens de région, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG> .

5.  Dans le menu **modifier** , sélectionnez **supprimer**.

6.  Cliquez sur **OK**.


## <a name="see-also"></a>Voir aussi

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
