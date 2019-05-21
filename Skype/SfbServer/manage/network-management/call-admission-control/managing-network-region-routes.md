---
title: Gestion des itinéraires de région réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Un itinéraire de région réseau définit l’itinéraire entre deux régions du réseau. Chaque paire de zones réseau dans le déploiement de votre contrôle d’admission des appels nécessite un itinéraire de la région du réseau.
ms.openlocfilehash: 174fdd021655f3e338001582a1409107b266582e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279507"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Gestion d’itinéraires de région réseau dans Skype Entreprise Server

Un *itinéraire de région réseau* définit l’itinéraire entre deux régions du réseau. Chaque paire de zones réseau dans le déploiement de votre contrôle d’admission des appels nécessite un itinéraire de la région du réseau. Cela permet à chaque région réseau incluse dans le déploiement d’accéder à toute autre région. Les procédures décrites dans cet Artilce vous permettent d’afficher, de créer, de modifier ou de supprimer des itinéraires de région réseau.

## <a name="view-network-region-route-information"></a>Afficher les informations sur les itinéraires de la région réseau 

Chaque région au sein d’une configuration de contrôle d’admission des appels (CAC) doit disposer d’un moyen d’accéder à toutes les autres régions. Lorsque les liaisons de zone définissent des limitations de bande passante pour les connexions entre les régions et représentent également les liens physiques, un itinéraire détermine le chemin d’accès lié que la connexion traverse d’une région à l’autre. Utilisez les procédures suivantes pour afficher les itinéraires des régions réseau existantes dans le panneau de configuration Skype entreprise Server ou Skype entreprise Server Management Shell. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>Pour afficher les informations sur le routage de la région réseau dans Skype entreprise Server panneau de configuration

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **itinéraire des régions**.

4.  Sur la page itinéraire de la **région** , cliquez sur le secteur que vous souhaitez afficher.


    > [!NOTE]  
    > Vous pouvez uniquement afficher un itinéraire par région à la fois.


5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations sur les itinéraires de région réseau à l’aide d’applets de requête Windows PowerShell

Les informations sur les itinéraires de région réseau peuvent être affichées à l’aide de Windows PowerShell et de l’applet de requête get-CsNetworkInterRegionRoute. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 

### <a name="to-view-network-region-route-information"></a>Pour afficher les informations relatives aux itinéraires de la région réseau

  - Pour afficher des informations sur l’ensemble des itinéraires de vos régions réseau, tapez la commande suivante dans le shell de gestion de Skype entreprise Server, puis appuyez sur entrée:
    
        Get-CsNetworkInterRegionRoute
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .


## <a name="create-or-modify-network-region-routes"></a>Créer ou modifier des itinéraires de région réseau

Chaque région au sein d’une configuration de contrôle d’admission des appels (CAC) doit disposer d’un moyen d’accéder à toutes les autres régions. Lorsque les liaisons de zone définissent des limitations de bande passante pour les connexions entre les régions et représentent également les liens physiques, un itinéraire détermine le chemin d’accès lié que la connexion traverse d’une région à l’autre. Le panneau de configuration Skype entreprise Server vous permet de configurer des itinéraires de région réseau. Dans le panneau de configuration Skype entreprise Server, vous pouvez créer, modifier ou supprimer un itinéraire de la région du réseau. Utilisez cette rubrique pour créer ou modifier un itinéraire de la région du réseau. 

### <a name="to-create-a-network-region-route"></a>Pour créer un itinéraire de la région du réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **itinéraire des régions**.

4.  Sur la page itinéraire de la **région** , cliquez sur **nouveau**.

5.  Dans la **zone nouvel itinéraire**de la région, tapez une valeur dans le champ **nom** .
   
    > [!NOTE]  
    > Cette valeur doit être unique dans le cadre de votre déploiement Skype entreprise Server.

6.  Dans la liste déroulante ** \#région de réseau 1** , sélectionnez l’une des deux régions auxquelles vous voulez être connectée par cet itinéraire.

7.  Dans la liste déroulante de la ** \#région réseau 2** , sélectionnez une autre région pour ce routage. Cette région doit être différente de la région sélectionnée pour la région \#réseau 1.

8.  Utilisez la zone de liste **liaisons de région réseau** pour ajouter des liens de région à l’itinéraire. Cliquez sur le bouton **Ajouter** pour afficher la page de liaison de la **zone** . Cliquez sur le lien d’une région pour l’ajouter à ce routage, puis cliquez sur **OK**.
    
    > [!NOTE]  
    > Continuez à cliquer sur le bouton **Ajouter** pour ajouter d’autres liens, ou sélectionnez un lien et cliquez sur **supprimer** pour supprimer un lien.

9.  Cliquez sur **Valider**.


### <a name="to-modify-a-network-region-route"></a>Pour modifier un itinéraire de la région du réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **itinéraire des régions**.

4.  Sur la page itinéraire de la **région** , cliquez sur le secteur que vous voulez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la **zone modifier le routage**des régions, vous pouvez modifier les régions jointes par cet itinéraire et les liaisons de région associées à l’itinéraire.

7.  Cliquez sur **Valider**.


## <a name="delete-existing-network-region-routes"></a>Supprimer des itinéraires de région réseau existants

Chaque région au sein d’une configuration de contrôle d’admission des appels (CAC) doit disposer d’un moyen d’accéder à toutes les autres régions. Lorsque les liaisons de zone définissent des limitations de bande passante pour les connexions entre les régions et représentent également les liens physiques, un itinéraire détermine le chemin d’accès lié que la connexion traverse d’une région à l’autre. Le panneau de configuration Skype entreprise Server vous permet de configurer des itinéraires de région réseau. Dans le panneau de configuration Skype entreprise Server, vous pouvez créer, modifier ou supprimer un itinéraire de la région du réseau. Utilisez cette rubrique pour supprimer des itinéraires de la région de réseau existants. 

### <a name="to-delete-a-network-region-route"></a>Pour supprimer un itinéraire de la région du réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **itinéraire des régions**.

4.  Sur la page itinéraire de la **région** , cliquez sur le secteur que vous voulez supprimer.

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs itinéraires par région à la fois. Pour cela, appuyez sur CTRL et sélectionnez plusieurs itinéraires de région tout en maintenant la touche CTRL enfoncée. Pour sélectionner tous les itinéraires de région, cliquez sur **Sélectionner tout** dans le menu **édition** .

5.  Dans le menu **modifier** , cliquez sur **supprimer**.

6.  Cliquez sur **OK**.



## <a name="see-also"></a>Voir aussi

[Gestion des régions réseau dans Skype Entreprise Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
