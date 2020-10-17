---
title: 'Lync Server 2013 : configuration du DNS pour la découverte automatique'
description: 'Lync Server 2013 : configuration du DNS pour la découverte automatique.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98a56cf3aa260bcbec9099e65958a9b17c3eaf26
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548460"
---
# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Configuration de DNS pour la découverte automatique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-12-12_

Pour prendre en charge la découverte automatique pour les clients Lync, vous devez créer les enregistrements DNS (Domain Name System) suivants :

  - Un enregistrement DNS interne pour prendre en charge les clients Lync qui se connectent à partir du réseau de votre organisation ;

  - Un enregistrement DNS externe ou public pour prendre en charge les clients Lync qui se connectent à partir d’Internet

Vous devez créer un enregistrement DNS interne et un enregistrement DNS externe pour chaque domaine SIP.

Les enregistrements DNS peuvent être des enregistrements A (hôte) ou CNAMe, en fonction de votre capacité à créer des certificats avec l’autre nom de l’objet (SAN). Si vous n’êtes pas en mesure de demander et de déployer un nouveau certificat externe (public) avec le lyncdiscover.\<domain name\> SAN, utilisez la procédure d’utilisation du port HTTP/TCP 80. Les procédures suivantes décrivent comment créer des enregistrements DNS internes et externes.

<div>

## <a name="to-create-dns-cname-records"></a>Pour créer des enregistrements CNAME DNS

1.  Ouvrez une session sur un serveur DNS comme suit :
    
      - Pour créer un enregistrement DNS interne, ouvrez une session sur un serveur DNS de votre réseau en tant que membre du groupe Administrateurs du domaine ou DnsAdmins.
    
      - Pour créer un enregistrement DNS externe, connectez-vous à votre fournisseur DNS public.

2.  Ouvrez le composant logiciel enfichable DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

3.  Effectuez l’une des opérations suivantes :
    
      - Pour un enregistrement DNS interne, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine Active Directory (par exemple, contoso.local).
        
        <div>
        

        > [!NOTE]  
        > Ce domaine est le domaine Active Directory dans lequel votre pool directeur et votre pool frontal Lync Server 2013 &nbsp; sont installés.

        
        </div>
    
      - Pour un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).

4.  Vérifiez qu’un enregistrement hôte A existe pour votre pool Directeur, comme suit :
    
      - Pour un enregistrement DNS interne, il doit exister un enregistrement A d’hôte pour le nom de domaine complet (FQDN) des services Web internes pour votre pool directeur (par exemple, lyncwebdir01. contoso. local).
    
      - Pour un enregistrement DNS externe, il doit exister un enregistrement A d’hôte pour le nom de domaine complet des services Web externes pour votre pool directeur (par exemple, lyncwebextdir.contoso.com).

5.  Vérifiez qu’il existe un enregistrement A d’hôte pour votre pool frontal comme suit :
    
      - Pour un enregistrement DNS interne, il doit exister un enregistrement A d’hôte pour le nom de domaine complet des services Web internes pour votre pool frontal (par exemple, lyncwebpool01. contoso. local).
    
      - Pour un enregistrement DNS externe, il doit exister un enregistrement A d’hôte pour le nom de domaine complet des services Web externes pour votre pool frontal (par exemple, lyncwebextpool01.contoso.com).

6.  Pour un enregistrement DNS interne, dans l’arborescence de la console de votre serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).
    
    <div>
    

    > [!NOTE]  
    > Si vous créez un enregistrement DNS externe, <STRONG>Zones de recherche directes</STRONG> est déjà développé pour votre domaine SIP (suite à l’étape 3).

    
    </div>

7.  Cliquez avec le bouton droit sur le nom du domaine SIP, puis cliquez sur **Nouvel alias (CNAME)**.

8.  Dans **Nom de l’alias**, tapez l’un des éléments suivants :
    
      - Pour un enregistrement DNS interne, tapez lyncdiscoverinternal comme nom d’hôte pour l’URL du service de découverte automatique interne.
    
      - Pour un enregistrement DNS externe, tapez lyncdiscover comme nom d’hôte pour l’URL du service de découverte automatique externe.

9.  Dans **Nom de domaine complet (FQDN) pour l’hôte de destination**, effectuez l’une des opérations suivantes :
    
      - Pour un enregistrement DNS interne, tapez ou recherchez le nom de domaine complet (FQDN) des services Web internes pour votre pool directeur (par exemple, lyncwebdir01. contoso. local), puis cliquez sur **OK**.
    
      - Pour un enregistrement DNS externe, tapez ou recherchez le nom de domaine complet (FQDN) des services Web externes pour votre pool directeur (par exemple, lyncwebextdir.contoso.com), puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Si vous n’utilisez pas de directeur, utilisez le nom de domaine complet des services Web internes et externes pour le pool frontal ou, pour un serveur unique, le nom de domaine complet (FQDN) du serveur frontal ou du serveur Standard Edition.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Vous devez créer un enregistrement CNAMe de découverte automatique dans la zone de recherche directe de chaque domaine SIP que vous prenez en charge dans votre environnement Lync Server 2013.

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>Pour créer des enregistrements A DNS

1.  Ouvrez une session sur un serveur DNS comme suit :
    
      - Pour créer un enregistrement DNS interne, ouvrez une session sur un serveur DNS de votre réseau en tant que membre du groupe Administrateurs du domaine ou DnsAdmins.
    
      - Pour créer un enregistrement DNS externe, connectez-vous à votre fournisseur DNS public ou à votre serveur DNS externe.

2.  Ouvrez le composant logiciel enfichable DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

3.  Effectuez l’une des opérations suivantes :
    
      - Pour un enregistrement DNS interne, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine Active Directory (par exemple, contoso.local).
        
        <div>
        

        > [!NOTE]  
        > Ce domaine est le domaine Active Directory dans lequel votre pool directeur et votre pool frontal Lync Server 2013 &nbsp; sont installés.

        
        </div>
    
      - Pour un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).

4.  Vérifiez qu’il existe un enregistrement A (pour IPv6, AAAA) hôte pour votre pool Directeur, comme suit :
    
      - Pour un enregistrement DNS interne, il doit exister un enregistrement A (pour IPv6, AAAA) hôte pour le nom de domaine complet des services Web internes pour votre pool directeur (par exemple, lyncwebdir01. contoso. local).
    
      - Pour un enregistrement DNS externe, il doit exister un enregistrement A (pour IPv6, AAAA) hôte pour le nom de domaine complet des services Web externes pour votre pool directeur (par exemple, lyncwebextdir.contoso.com).

5.  Vérifiez qu’il existe un enregistrement A (pour IPv6, AAAA) hôte pour votre pool frontal comme suit :
    
      - Pour un enregistrement DNS interne, il doit exister un enregistrement A (pour IPv6, AAAA) hôte pour le nom de domaine complet des services Web internes pour votre pool frontal (par exemple, lyncwebpool01. contoso. local).
    
      - Pour un enregistrement DNS externe, il doit exister un enregistrement A (pour IPv6, AAAA) hôte pour le nom de domaine complet des services Web externes pour votre pool frontal (par exemple, lyncwebextpool01.contoso.com).

6.  Pour un enregistrement DNS interne, dans l’arborescence de la console de votre serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).
    
    <div>
    

    > [!NOTE]  
    > Si vous créez un enregistrement DNS externe, <STRONG>Zones de recherche directes</STRONG> est déjà développé pour votre domaine SIP (suite à l’étape 3).

    
    </div>

7.  Cliquez avec le bouton droit sur le nom du domaine SIP, puis cliquez sur **Nouvel hôte (A ou AAAA)**.

8.  Dans **Nom**, tapez le nom d’hôte comme suit :
    
      - Pour un enregistrement DNS interne, tapez lyncdiscoverinternal comme nom d’hôte pour l’URL du service de découverte automatique interne.
    
      - Pour un enregistrement DNS externe, tapez lyncdiscover comme nom d’hôte pour l’URL du service de découverte automatique externe.
    
    <div>
    

    > [!NOTE]  
    > Le nom de domaine est déduit d’après la zone dans laquelle l’enregistrement est défini ; il est par conséquent inutile de l’entrer dans le cadre de l’enregistrement A.

    
    </div>

9.  Dans **Adresse IP**, tapez l’adresse IP comme suit :
    
      - Pour un enregistrement DNS interne, tapez l’adresse IP interne des services Web du directeur (ou, si vous utilisez un programme d’équilibrage de la charge, tapez l’adresse IP virtuelle de l’équilibreur de charge du directeur).
        
        <div>
        

        > [!NOTE]  
        > Si vous n’utilisez pas de directeur, tapez l’adresse IP du serveur frontal ou du serveur Standard Edition, ou si vous utilisez un programme d’équilibrage de la charge, tapez l’adresse IP du programme d’équilibrage de la charge du pool frontal.

        
        </div>
    
      - Pour un enregistrement DNS externe, tapez l’adresse IP externe ou publique du proxy inverse.

10. Cliquez sur **Ajouter un hôte**, puis sur **OK**.

11. Pour créer un enregistrement A supplémentaire, répétez les étapes 8 à 10.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous devez créer un nouveau lyncdiscover et lyncdiscoverinternal des enregistrements A dans la zone de recherche directe de chaque domaine SIP que vous prenez en charge dans votre environnement Lync Server 2013.

    
    </div>

12. Lorsque vous avez terminé de créer des enregistrements A (AAAA pour IPv6), cliquez sur **Terminé**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

