---
title: 'Lync Server 2013 : création ou modification de sites réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67d4fedf5931a85772e42a87fb80c382a364ae96
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>Création ou modification de sites réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-08_

Les sites réseau sont les bureaux ou emplacements configurés au sein de chaque région d’un contrôle d’admission des appels (Call Admission Control ou CAC) ou encore d’un déploiement Enhanced 9-1-1. Vous pouvez utiliser le panneau de configuration Microsoft Lync Server 2013 pour configurer des sites et les associer à des régions. Par exemple, vous pouvez associer la région réseau Amérique du Nord à des sites réseau, tels que Chicago, Redmond et Vancouver. Un site réseau CAC doit être créé pour chaque site dans l’organisation, même en l’absence de limitation de bande passante pour ce site. Dans le panneau de configuration Lync Server, vous pouvez créer, modifier et supprimer des sites réseau. Utilisez les procédures suivantes pour créer ou modifier un site réseau. Pour plus d’informations sur la suppression d’un site réseau existant, reportez-vous à [la rubrique Suppression d’un site réseau existant dans Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).

<div>

## <a name="to-create-a-network-site"></a>Pour créer un site réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Site**.

4.  Dans la page **Site**, cliquez sur **Nouveau**.

5.  Dans **Nouveau site**, renseignez le champ **Nom**.
    
    <div>
    

    > [!NOTE]  
    > Les noms de site doivent être uniques dans le déploiement Lync Server 2013.

    
    </div>

6.  Dans la liste déroulante **Région**, sélectionnez une région réseau à associer au site.

7.  (Facultatif) Si vous voulez imposer sur ce site des limitations de bande passante aux appels audio ou vidéo, sélectionnez le profil de stratégie de bande passante adéquat dans la liste déroulante **Stratégie de bande passante**.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez afficher les détails des profils de stratégie de bande passante ou créer un profil dans la page <STRONG>Profil de stratégie</STRONG> du groupe <STRONG>Configuration du réseau</STRONG>. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">la rubrique création ou modification de profils de stratégie de bande passante dans Lync Server 2013</A>.

    
    </div>

8.  (Facultatif) Si vous voulez spécifier des paramètres d’emplacement pour ce site, sélectionnez une stratégie d’emplacement dans la liste déroulante **Stratégie d’emplacement**.
    
    <div>
    

    > [!NOTE]  
    > La stratégie d’emplacement affecte les paramètres Enhanced 9-1-1 (E9-1-1) et d’emplacement des clients au site. Vous pouvez afficher les détails des stratégies d’emplacement ou créer une stratégie d’emplacement dans la page <STRONG>Stratégie d’emplacement</STRONG> du groupe <STRONG>Configuration du réseau</STRONG>. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-viewing-location-policy-information.md">affichage des informations de stratégie d’emplacement dans Lync Server 2013</A>.

    
    </div>

9.  (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce site, car son nom ne suffit pas à le décrire.

10. Cliquez sur **Valider**.
    
    <div>
    

    > [!NOTE]  
    > Lors de la création d’un site réseau, vous n’utilisez pas la table <STRONG>Sous-réseaux associés</STRONG>. Vous associez un sous-réseau à un site lorsque vous créez ou modifiez le sous-réseau. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-create-or-modify-network-subnets.md">créer ou modifier des sous-réseaux réseau dans Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>Pour modifier un site réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Site**.

4.  Dans la page **Site**, cliquez sur le site que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier le site**, vous pouvez modifier la description, la région, le profil de la stratégie de bande passante et la stratégie d’emplacement associés au site. Pour plus d’informations, voir « Pour créer un site réseau » plus haut dans cette rubrique.

7.  Cliquez sur **Valider**.

Vous ne pouvez pas modifier la table **Sous-réseaux associés** de cette page. La liste de sous-réseaux associés est donnée à titre de référence de sorte que vous sachiez quels sous-réseaux seront affectés par les paramètres que vous modifiez.

</div>

<div>

## <a name="to-delete-a-network-site"></a>Pour supprimer un site réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Site**.

4.  Dans la page **Site**, cliquez sur le site que vous souhaitez supprimer.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs sites à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs sites. Ou, pour sélectionner tous les sites, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.

    
    </div>

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.
    
    <div>
    

    > [!WARNING]  
    > Vous ne pouvez pas supprimer un site réseau associé à un sous-réseau de réseau. Si vous essayez, vous recevrez un message d’erreur. Pour savoir si un site est associé à des sous-réseaux, cliquez sur le site, puis sur <STRONG>Afficher les détails</STRONG> dans le menu <STRONG>Edition</STRONG>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Suppression d’un site réseau existant dans Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md)  


[New-applet csnetworksite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[Set-applet csnetworksite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[Remove-applet csnetworksite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[Get-applet csnetworksite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

