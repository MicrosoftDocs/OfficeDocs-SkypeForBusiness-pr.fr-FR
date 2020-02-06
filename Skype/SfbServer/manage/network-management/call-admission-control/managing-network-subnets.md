---
title: Gestion des sous-réseaux réseau
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
description: Dans la plupart des déploiements de Skype entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il existe généralement un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer les sous-réseaux à partir de Skype entreprise Server Management Shell.
ms.openlocfilehash: fd7d71b3971b176939967830ca3e071ef4c77dbf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817463"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Gestion des sous-réseaux réseau dans Skype Entreprise Server

Vous pouvez utiliser le panneau de configuration Skype entreprise Server ou Skype entreprise Server Management Shell pour gérer les sous-réseaux du réseau. Dans la plupart des déploiements de Skype entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il existe généralement un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer les sous-réseaux à partir de Skype entreprise Server Management Shell.

Les sections de cet article vous permettent d’afficher les informations de sous-réseau ou de créer, modifier ou supprimer des sous-réseaux réseau. 

## <a name="view-network-subnet-information"></a>Afficher les informations de sous-réseau 

Vous pouvez utiliser la procédure suivante pour afficher un sous-réseau. Dans le panneau de configuration Skype entreprise Server, vous pouvez créer, modifier ou supprimer un sous-réseau. 

### <a name="to-view-a-network-subnet"></a>Pour afficher un sous-réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **sous-réseau**.

4.  Dans la page de **sous-réseau** , cliquez sur le sous-réseau que vous souhaitez afficher.
 
    > [!NOTE]  
    > Vous ne pouvez afficher qu’un seul sous-réseau à la fois.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Afficher les informations de configuration de sous-réseau en utilisant des applets de cmdlet Windows PowerShell

Les informations de sous-réseau peuvent être affichées à l’aide de Windows PowerShell et de l’applet de connexion Get-CsNetworkSubnet. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 

### <a name="to-view-network-subnet-information"></a>Pour afficher les informations de sous-réseau

  - Pour afficher des informations sur tous les sous-réseaux de votre réseau, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :
    
        Get-CsNetworkSubnet
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .


## <a name="create-or-modify-network-subnets"></a>Créer ou modifier des sous-réseaux réseau 

Un sous-réseau doit être associé à un site réseau pour vous permettre de déterminer l’emplacement géographique de l’hôte appartenant à ce sous-réseau. Le panneau de configuration Skype entreprise Server vous permet de configurer les sous-réseaux. Dans le panneau de configuration Skype entreprise Server, vous pouvez créer, modifier ou supprimer un sous-réseau. 

Dans la plupart des déploiements de Skype entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il existe généralement un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer les sous-réseaux à partir de Skype entreprise Server Management Shell. À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’applet de cmdlet Windows PowerShell **Import-CSV**. L’utilisation conjointe de ces applets de passe vous permet de lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (. csv) et de créer plusieurs sous-réseaux en même temps. Pour obtenir des exemples sur la façon de créer des sous-réseaux à partir d’un fichier. csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-create-a-network-subnet"></a>Pour créer un sous-réseau du réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **sous-réseau**.

4.  Sur la page **sous-réseau** , cliquez sur **nouveau**.

5.  Dans **nouveau sous-réseau**, entrez une valeur dans le champ **ID de sous-réseau** . Il doit s’agir d’une adresse IP (par exemple, 174.11.12.0) et doit être la première adresse de la plage d’adresses IP définie par le sous-réseau.

6.  Dans le champ **masque** , entrez une valeur numérique comprise entre 1 et 32.

    > [!NOTE]  
    > Cette valeur correspond au masque de passe à appliquer au sous-réseau qui est créé.

7.  Dans **ID du site réseau**, sélectionnez le site auquel appartient ce sous-réseau.

8.  Facultatif Tapez une valeur dans le champ **Description** pour fournir davantage d’informations sur ce sous-réseau qui ne peut pas être exprimé par le nom seul.

9.  Cliquez sur **Valider**.


### <a name="to-modify-a-network-subnet"></a>Pour modifier un sous-réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **sous-réseau**.

4.  Dans la page de **sous-réseau** , cliquez sur le sous-réseau que vous voulez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **modifier le sous-réseau** , vous pouvez modifier le masque de la page, le site réseau associé ou la description. Si vous modifiez le masque de réinitialisation, n’oubliez pas que l’ID de sous-réseau doit toujours être la première adresse de la plage d’adresses IP définie par le sous-réseau.

7.  Cliquez sur **Valider**.

## <a name="delete-network-subnets"></a>Supprimer des sous-réseaux réseau

Vous pouvez utiliser la procédure suivante pour supprimer un sous-réseau. Dans le panneau de configuration Skype entreprise Server, vous pouvez créer, modifier ou supprimer un sous-réseau. 

Dans la plupart des déploiements de Skype entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il existe généralement un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer les sous-réseaux à partir de Skype entreprise Server Management Shell. À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’applet de cmdlet Windows PowerShell **Import-CSV**. L’utilisation conjointe de ces applets de passe vous permet de lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (. csv) et de créer plusieurs sous-réseaux en même temps. Pour obtenir des exemples sur la façon de créer des sous-réseaux à partir d’un fichier. csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-delete-a-network-subnet"></a>Pour supprimer un sous-réseau du réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **sous-réseau**.

4.  Dans la page de **sous-réseau** , cliquez sur le sous-réseau que vous voulez supprimer.
 
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs sous-réseaux à la fois. Pour cela, appuyez sur CTRL et sélectionnez plusieurs sous-réseaux tout en maintenant la touche CTRL enfoncée. Pour sélectionner tous les sous-réseaux, cliquez sur **tout sélectionner** dans le menu **Edition** .

5.  Dans le menu **modifier** , cliquez sur **supprimer**.

6.  Cliquez sur **OK**.


## <a name="see-also"></a>Voir aussi

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
