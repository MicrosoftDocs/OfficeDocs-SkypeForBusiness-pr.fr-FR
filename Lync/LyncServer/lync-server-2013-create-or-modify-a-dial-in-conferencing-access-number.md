---
title: 'Lync Server 2013 : création ou modification d’un numéro d’accès à une conférence rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f684166c7a33f092ee9d7a00eb9582cb70e2606
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Création ou modification d’un numéro d’accès à une conférence rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-17_

Procédez comme suit pour créer ou modifier un numéro d’accès à une conférence rendez-vous.

<div>


> [!IMPORTANT]  
> Avant de créer un numéro d’accès entrant, vous devez définir une région de conférence rendez-vous dans le plan de numérotation associé au nouveau numéro d’accès entrant. Plusieurs plans de numérotation peuvent utiliser la même région.



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a>Pour créer ou modifier un numéro d’accès entrant

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.

4.  Sur la page **numéro d’accès entrant** , effectuez l’une des opérations suivantes :
    
      - Cliquez sur **nouveau** pour ouvrir **le nouveau numéro d’accès entrant**.
    
      - Cliquez sur l’un des numéros d’accès entrant dans la liste, cliquez sur **modifier**, puis sur **afficher les détails**.
        
        <div>
        

        > [!NOTE]  
        > L’utilisation du champ de recherche pour rechercher le contenu d’une colonne dans la liste des numéros d’accès entrant peut ne pas donner les résultats attendus. Au lieu de cela, triez la liste selon la colonne qui vous intéresse pour identifier le numéro d’accès entrant que vous souhaitez afficher ou modifier.

        
        </div>

5.  Dans **numéro affiché**, tapez le numéro de téléphone que les utilisateurs du téléphone du réseau téléphonique commuté (PSTN) composent pour rejoindre une conférence.
    
    <div>
    

    > [!NOTE]  
    > Ce numéro est affiché dans les invitations aux réunions et dans la page Web des paramètres de conférence rendez-vous.

    
    </div>

6.  Dans **nom d’affichage**, tapez une description pour le numéro d’accès entrant. Il s’agit du nom associé au numéro d’accès entrant dans les résultats de la recherche Lync.
    
    <div>
    

    > [!NOTE]  
    > Ce nom s’affiche dans le client lorsqu’un utilisateur appelle le numéro d’accès.

    
    </div>

7.  Dans **URI de ligne**, tapez le numéro E. 164 du numéro d’accès entrant au format URI tel, y compris le symbole + avant le numéro et en excluant les espaces. Par exemple, Tél : + 14255550200.
    
    <div>
    

    > [!NOTE]  
    > Le même URI de ligne ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous.

    
    </div>

8.  Dans **URI SIP**, procédez comme suit :
    
      - Dans la zone de texte, tapez un URI SIP unique pour ce numéro d’accès à la Conférence rendez-vous. Cet URI SIP est affiché à différents emplacements, y compris, sans s’y limiter, les messages de notification d’appel et les versions antérieures des clients Communicator.
        
        <div>
        

        > [!NOTE]  
        > Le même URI SIP ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous. L’URI SIP ne peut pas être modifié une fois que le numéro d’accès est créé. La seule façon de modifier l’URI SIP est de supprimer et de recréer le numéro d’accès.

        
        </div>
    
      - Dans la zone de liste déroulante, cliquez sur le domaine de l’application de surveillance de conférence qui prend en charge ce numéro d’accès entrant.

9.  Dans **pool**, cliquez sur le pool qui exécute l’instance du service Surveillance de conférence qui prend en charge ce numéro d’accès entrant.
    
    <div>
    

    > [!NOTE]  
    > Si vous devez modifier le pool après avoir créé le numéro d’accès, vous devez utiliser l’applet de commande <STRONG>Move-CsApplicationEndpoint</STRONG> ou supprimer et recréer le numéro d’accès.

    
    </div>

10. Dans **langue principale**, cliquez sur la langue dans laquelle les invites sont exécutées pour ce numéro d’accès entrant.
    
    <div>
    

    > [!NOTE]  
    > La langue principale est la langue utilisée par le service Surveillance de conférence pour répondre à l’appel. Les langues prises en charge sont affichées avec chaque numéro de téléphone d’accès dans la page Web paramètres de conférence rendez-vous.

    
    </div>

11. Module Dans **langues secondaires (quatre au maximum)**, cliquez sur **Ajouter**, sélectionnez une ou plusieurs langues supplémentaires que vous souhaitez prendre en charge pour les appelants vers ce numéro d’accès entrant, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez choisir jusqu’à quatre langues secondaires pour chaque numéro d’accès entrant. Les utilisateurs peuvent sélectionner une langue secondaire avant d’entrer l’ID de conférence lorsqu’ils se connectent à une conférence.

    
    </div>

12. Pour ajouter une région pour le numéro d’accès entrant, sous **régions associées**, cliquez sur **Ajouter**, cliquez sur une ou plusieurs régions associées aux plans de numérotation pour ce numéro d’accès entrant, puis cliquez sur **OK**.

13. Pour supprimer une région du numéro d’accès entrant, sous **régions associées**, cliquez sur la région que vous souhaitez supprimer, puis cliquez sur **supprimer**.

14. Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

