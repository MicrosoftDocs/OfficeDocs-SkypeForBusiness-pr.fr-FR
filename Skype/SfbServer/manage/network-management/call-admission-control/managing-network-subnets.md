---
title: Gestion des sous-réseaux
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dans la plupart des déploiements Skype pour Business Server où le contrôle d’admission des appels (CAC) est implémenté, généralement sera un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de la Skype pour Business Server Management Shell.
ms.openlocfilehash: 3b61ad1b4e1eb7f11d61b32c15e337bcd4ff77c8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899749"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Gestion des sous-réseaux réseau dans Skype Entreprise Server

Vous pouvez utiliser soit le Skype pour le panneau de configuration serveur Business ou le Skype pour Business Server Management Shell pour gérer les sous-réseaux. Dans la plupart des déploiements Skype pour Business Server où le contrôle d’admission des appels (CAC) est implémenté, généralement sera un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de la Skype pour Business Server Management Shell.

Utilisez les sections de cet article pour afficher les informations de sous-réseau de réseau ou créer, modifier ou supprimer des sous-réseaux. 

## <a name="view-network-subnet-information"></a>Afficher les informations de sous-réseau de réseau 

Vous pouvez utiliser la procédure suivante pour afficher un sous-réseau de réseau. À partir de Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier ou supprimer un sous-réseau de réseau. 

### <a name="to-view-a-network-subnet"></a>Pour afficher un sous-réseau de réseau

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **sous-réseau**.

4.  Dans la page **sous-réseau** , cliquez sur le sous-réseau que vous souhaitez afficher.
 
    > [!NOTE]  
    > Vous ne pouvez afficher qu’un seul sous-réseau à la fois.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Afficher les informations de configuration de sous-réseau de réseau à l’aide de cmdlets Windows PowerShell

Informations relatives au sous-réseau peuvent être affichés à l’aide de Windows PowerShell et l’applet de commande Get-CsNetworkSubnet. Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. 

### <a name="to-view-network-subnet-information"></a>Pour afficher les informations de sous-réseau de réseau

  - Pour afficher des informations sur tous les sous-réseaux de votre réseau, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :
    
        Get-CsNetworkSubnet
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .


## <a name="create-or-modify-network-subnets"></a>Créer ou modifier des sous-réseaux 

Un sous-réseau de réseau doit être associé à un site réseau à des fins de détermination de l’emplacement géographique de l’hôte appartenant à ce sous-réseau. Vous pouvez utiliser la Skype pour Business Server Control Panel pour configurer des sous-réseaux. À partir de Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier ou supprimer un sous-réseau de réseau. 

Dans la plupart des déploiements Skype pour Business Server où le contrôle d’admission des appels (CAC) est implémenté, généralement sera un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de la Skype pour Business Server Management Shell. À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’applet de commande Windows PowerShell **Import-CSV**. L’utilisation conjointe de ces applets de commande, vous pouvez lire les paramètres de sous-réseau dans un fichier de valeurs séparées par des virgules (.csv) et créer plusieurs sous-réseaux en même temps. Pour obtenir des exemples illustrant comment créer des sous-réseaux à partir d’un fichier .csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-create-a-network-subnet"></a>Pour créer un sous-réseau de réseau

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **sous-réseau**.

4.  Dans la page **sous-réseau** , cliquez sur **Nouveau**.

5.  Dans **Nouveau sous-réseau**, entrez une valeur dans le champ **ID de sous-réseau** . Il doit s’agir d’une adresse IP (par exemple, 174.11.12.0), et elle doit être la première adresse de la plage d’adresses IP définie par le sous-réseau.

6.  Dans le champ **masque** , entrez une valeur numérique comprise entre 1 et 32.

    > [!NOTE]  
    > Cette valeur est le masque de bits à appliquer au sous-réseau créé.

7.  **ID de site réseau**, sélectionnez le site auquel ce sous-réseau appartient.

8.  (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce sous-réseau ne suffit pas au nom seul.

9.  Cliquez sur **Valider**.


### <a name="to-modify-a-network-subnet"></a>Pour modifier un sous-réseau de réseau

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **sous-réseau**.

4.  Dans la page **sous-réseau** , cliquez sur le sous-réseau que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier un sous-réseau** , vous pouvez modifier le masque de bits, le site réseau associé ou la description. Si vous modifiez le masque de bits, n’oubliez pas que l’ID de sous-réseau doit être toujours la première adresse de la plage d’adresses IP définie par le sous-réseau.

7.  Cliquez sur **Valider**.

## <a name="delete-network-subnets"></a>Supprimer les sous-réseaux

Vous pouvez utiliser la procédure suivante pour supprimer un sous-réseau. À partir de Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier ou supprimer un sous-réseau de réseau. 

Dans la plupart des déploiements Skype pour Business Server où le contrôle d’admission des appels (CAC) est implémenté, généralement sera un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de la Skype pour Business Server Management Shell. À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’applet de commande Windows PowerShell **Import-CSV**. L’utilisation conjointe de ces applets de commande, vous pouvez lire les paramètres de sous-réseau dans un fichier de valeurs séparées par des virgules (.csv) et créer plusieurs sous-réseaux en même temps. Pour obtenir des exemples illustrant comment créer des sous-réseaux à partir d’un fichier .csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-delete-a-network-subnet"></a>Pour supprimer un sous-réseau de réseau

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **sous-réseau**.

4.  Dans la page **sous-réseau** , cliquez sur le sous-réseau que vous souhaitez supprimer.
 
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs sous-réseaux à la fois. Pour ce faire, appuyez sur la touche CTRL ENFONCÉE et sélectionnez plusieurs sous-réseaux tout en maintenant la touche CTRL enfoncée. Ou, pour sélectionner tous les sous-réseaux, cliquez sur **Sélectionner tout** dans le menu **Edition** .

5.  Dans le menu **Edition** , cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.


## <a name="see-also"></a>Voir aussi

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
