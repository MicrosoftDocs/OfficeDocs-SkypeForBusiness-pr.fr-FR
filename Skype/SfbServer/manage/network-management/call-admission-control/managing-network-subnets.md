---
title: Gestion des sous-réseaux
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
description: Dans la plupart des déploiements de Skype Entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il y a généralement un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de Skype Entreprise Server Management Shell.
ms.openlocfilehash: d7abe489d6424cf7a1468060b54d5df99b123bf4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740480"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Gestion des sous-réseaux réseau dans Skype Entreprise Server

Vous pouvez utiliser le Panneau de Skype Entreprise Server ou l’Skype Entreprise Server Management Shell pour gérer les sous-réseaux. Dans la plupart des déploiements de Skype Entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il y a généralement un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de Skype Entreprise Server Management Shell.

Utilisez les sections de cet article pour afficher des informations sur les sous-réseaux ou créer, modifier ou supprimer des sous-réseaux. 

## <a name="view-network-subnet-information"></a>Afficher les informations de sous-réseau 

Vous pouvez utiliser la procédure suivante pour afficher un sous-réseau. À partir Skype Entreprise Server panneau de bord, vous pouvez créer, modifier ou supprimer un sous-réseau. 

### <a name="to-view-a-network-subnet"></a>Pour afficher un sous-réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration** réseau, puis sur **Sous-réseau.**

4.  Dans la page **Sous-réseau**, cliquez sur le sous-réseau que vous souhaitez afficher.
 
    > [!NOTE]
    > Vous ne pouvez afficher qu’un seul sous-réseau à la fois.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Afficher les informations de configuration de sous-réseau à l’aide Windows PowerShell cmdlets

Les informations de sous-réseau peuvent être vues à l’aide Windows PowerShell et de la cmdlet Get-CsNetworkSubnet réseau. Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 

### <a name="to-view-network-subnet-information"></a>Pour afficher les informations de sous-réseau

  - Pour afficher des informations sur tous vos sous-réseaux, tapez la commande suivante dans l’Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
    **Get-CsNetworkSubnet**
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
    Identité : 172.11.15.0<br/>
    MaskBits : 28<br/>
    Description :<br/>
    NetworkSiteID : Redmond<br/>
    SubnetID : 172.11.15.0<br/>


Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet).


## <a name="create-or-modify-network-subnets"></a>Créer ou modifier des sous-réseaux réseau 

Un sous-réseau de réseau doit être associé à un site réseau afin de déterminer l’emplacement géographique de l’hôte appartenant à ce sous-réseau. Vous pouvez utiliser le Panneau de configuration Skype Entreprise Server pour configurer des sous-réseaux. À partir Skype Entreprise Server panneau de bord, vous pouvez créer, modifier ou supprimer un sous-réseau. 

Dans la plupart des déploiements de Skype Entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il y a généralement un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de Skype Entreprise Server Management Shell. À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’Windows PowerShell cmdlet **Import-CSV**. En utilisant ces cmdlets ensemble, vous pouvez lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (.csv) et créer plusieurs sous-réseaux en même temps. Pour obtenir des exemples de création de sous-réseaux à partir d.csv fichier, voir [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-create-a-network-subnet"></a>Pour créer un sous-réseau de réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration** réseau, puis sur **Sous-réseau.**

4.  Dans la page **Sous-réseau**, cliquez sur **Nouveau**.

5.  Dans **Nouveau sous-réseau**, entrez une valeur dans le champ **ID de sous-réseau**. Il doit s’agir d’une adresse IP (par exemple, 174.11.12.0), qui doit être la première adresse dans la plage d’adresses IP définie par le sous-réseau.

6.  Dans le champ **Masque**, entrez une valeur numérique comprise entre 1 et 32.

    > [!NOTE]  
    > Cette valeur est le masque de bits à appliquer au sous-réseau en cours de création.

7.  Dans le champ **ID de site réseau**, sélectionnez le site auquel ce sous-réseau appartient.

8.  (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce sous-réseau, car son nom ne suffit pas à le décrire.

9.  Cliquez sur **Valider**.


### <a name="to-modify-a-network-subnet"></a>Pour modifier un sous-réseau de réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration** réseau, puis sur **Sous-réseau.**

4.  Dans la page **Sous-réseau**, cliquez sur le sous-réseau que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier le sous-réseau**, vous pouvez modifier le masque de bits, le site réseau associé ou la description du sous-réseau. Si vous modifiez le masque de bits, n’oubliez pas que l’ID du sous-réseau doit toujours être la première adresse dans la plage d’adresses IP définie par le sous-réseau.

7.  Cliquez sur **Valider**.

## <a name="delete-network-subnets"></a>Supprimer des sous-réseaux réseau

La procédure suivante vous permet de supprimer un sous-réseau. À partir Skype Entreprise Server panneau de bord, vous pouvez créer, modifier ou supprimer un sous-réseau. 

Dans la plupart des déploiements de Skype Entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il y a généralement un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de Skype Entreprise Server Management Shell. À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’Windows PowerShell cmdlet **Import-CSV**. En utilisant ces cmdlets ensemble, vous pouvez lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (.csv) et créer plusieurs sous-réseaux en même temps. Pour obtenir des exemples de création de sous-réseaux à partir d.csv fichier, voir [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-delete-a-network-subnet"></a>Pour supprimer un sous-réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration** réseau, puis sur **Sous-réseau.**

4.  Dans la page **Sous-réseau**, cliquez sur le sous-réseau à supprimer.
 
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs sous-réseaux à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez les différents sous-réseaux à supprimer. Pour sélectionner la totalité des sous-réseaux, cliquez sur **Sélectionner tout** dans le menu **Edition**.

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.


## <a name="see-also"></a>Voir aussi

[New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet)