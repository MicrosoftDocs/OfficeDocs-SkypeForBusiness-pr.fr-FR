---
title: 'Lync Server 2013 : configuration du DNS pour la découverte automatique'
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
ms.openlocfilehash: 77cf81cd82655a37ad089d915e9e3799671025bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Configuration de DNS pour la découverte automatique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-12-12_

Pour prendre en charge la découverte automatique pour les clients Lync, vous devez créer les enregistrements DNS suivants :

  - Un enregistrement DNS interne pour la prise en charge des clients Lync qui se connectent au sein du réseau de votre organisation.

  - Enregistrement DNS externe ou public permettant de prendre en charge les clients Lync qui se connectent à partir d’Internet

Vous devez créer un enregistrement DNS interne et un enregistrement DNS externe pour chaque domaine SIP.

Les enregistrements DNS peuvent être des enregistrements CNAMe ou CNAMe, en fonction de votre capacité à créer des certificats avec le nouveau nom d’objet. Si vous n’êtes pas en mesure de demander et de déployer un nouveau certificat externe (public) avec le lyncdiscover. \<réseau de\> noms de domaine, utilisez la procédure d’utilisation du port 80 http/TCP. Les procédures suivantes décrivent la création d’enregistrements DNS internes et externes.

<div>

## <a name="to-create-dns-cname-records"></a>Pour créer des enregistrements CNAMe DNS

1.  Connectez-vous à un serveur DNS comme suit :
    
      - Pour créer un enregistrement DNS interne, connectez-vous à un serveur DNS de votre réseau en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.
    
      - Pour créer un enregistrement DNS externe, connectez-vous à votre fournisseur DNS public.

2.  Ouvrez le composant logiciel enfichable d’administration DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

3.  Effectuez l’une des actions suivantes :
    
      - Pour un enregistrement DNS interne, dans l’arborescence de la console du serveur DNS, développez la **zone de recherche directe** pour votre domaine Active Directory (par exemple, contoso. local).
        
        <div>
        

        > [!NOTE]  
        > Ce domaine est le domaine Active Directory dans lequel votre pool de&nbsp;directeurs Lync Server 2013 et votre pool frontal sont installés.

        
        </div>
    
      - Dans le cas d’un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com).

4.  Vérifiez qu’un enregistrement A existe pour votre pool de directeurs comme suit :
    
      - Dans le cas d’un enregistrement DNS interne, un enregistrement A doit exister pour le nom de domaine complet (FQDN) des services Web internes pour votre pool de répertoires (par exemple, lyncwebdir01. contoso. local).
    
      - Dans le cas d’un enregistrement DNS externe, un enregistrement de l’hôte A doit exister pour le nom de domaine complet des services Web externes de votre pool de directeurs (par exemple, lyncwebextdir.contoso.com).

5.  Vérifiez qu’un enregistrement A existe pour votre pool frontal comme suit :
    
      - Dans le cas d’un enregistrement DNS interne, un enregistrement A doit exister pour le nom de domaine complet des services Web internes de votre pool frontal (par exemple, lyncwebpool01. contoso. local).
    
      - Dans le cas d’un enregistrement DNS externe, un enregistrement de l’hôte A doit exister pour le nom de domaine complet des services Web externes de votre pool frontal (par exemple, lyncwebextpool01.contoso.com).

6.  Pour un enregistrement DNS interne, dans l’arborescence de la console de votre serveur DNS, développez **zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com).
    
    <div>
    

    > [!NOTE]  
    > Si vous créez un enregistrement DNS externe, les <STRONG>zones de recherche directe</STRONG> sont déjà développées pour votre domaine SIP à l’étape 3.

    
    </div>

7.  Cliquez avec le bouton droit sur le nom de domaine SIP, puis cliquez sur **Nouvel alias (CNAME)**.

8.  Dans **nom**de l’alias, tapez l’une des valeurs suivantes :
    
      - Pour un enregistrement DNS interne, tapez lyncdiscoverinternal comme nom d’hôte de l’URL du service de découverte automatique interne.
    
      - Pour un enregistrement DNS externe, tapez lyncdiscover comme nom d’hôte de l’URL du service de découverte automatique externe.

9.  Dans **nom de domaine complet (FQDN) de l’hôte cible**, effectuez l’une des opérations suivantes :
    
      - Pour un enregistrement DNS interne, tapez ou accédez au nom de domaine complet des services Web internes de votre pool de réalisateurs (par exemple, lyncwebdir01. contoso. local), puis cliquez sur **OK**.
    
      - Pour un enregistrement DNS externe, tapez ou accédez au nom de domaine complet des services Web externes de votre pool de réalisateurs (par exemple, lyncwebextdir.contoso.com), puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Si vous n’utilisez pas de réalisateur, utilisez le nom de domaine complet (FQDN) de services Web interne et externe pour le pool frontal, ou, pour un serveur unique, le nom de domaine complet (FQDN) du serveur frontal ou du serveur Standard Edition.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Vous devez créer un enregistrement CNAMe de découverte automatique dans la zone de recherche directe de chaque domaine SIP que vous prenez en charge dans votre environnement Lync Server 2013.

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>Pour créer des enregistrements DNS A

1.  Connectez-vous à un serveur DNS comme suit :
    
      - Pour créer un enregistrement DNS interne, connectez-vous à un serveur DNS de votre réseau en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.
    
      - Pour créer un enregistrement DNS externe, connectez-vous à votre fournisseur DNS public ou votre serveur DNS externe.

2.  Ouvrez le composant logiciel enfichable d’administration DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

3.  Effectuez l’une des actions suivantes :
    
      - Pour un enregistrement DNS interne, dans l’arborescence de la console du serveur DNS, développez la **zone de recherche directe** pour votre domaine Active Directory (par exemple, contoso. local).
        
        <div>
        

        > [!NOTE]  
        > Ce domaine est le domaine Active Directory dans lequel votre pool de&nbsp;directeurs Lync Server 2013 et votre pool frontal sont installés.

        
        </div>
    
      - Dans le cas d’un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com).

4.  Vérifiez qu’un enregistrement hôte A (pour IPv6, AAAA) existe pour votre pool de réalisateurs comme suit :
    
      - Dans le cas d’un enregistrement DNS interne, un enregistrement hôte A (pour IPv6, AAAA) doit exister pour le nom de domaine complet (FQDN) des services Web internes de votre pool de directeurs (par exemple, lyncwebdir01. contoso. local).
    
      - Dans le cas d’un enregistrement DNS externe, un enregistrement hôte A (pour IPv6, AAAA) doit exister pour le nom de domaine complet des services Web externes de votre pool de directeurs (par exemple, lyncwebextdir.contoso.com).

5.  Vérifiez qu’un enregistrement A (pour IPv6, AAAA) existe pour le pool frontal comme suit :
    
      - Dans le cas d’un enregistrement DNS interne, un enregistrement hôte A (pour IPv6, AAAA) doit exister pour le nom de domaine complet des services Web internes de votre pool frontal (par exemple, lyncwebpool01. contoso. local).
    
      - Dans le cas d’un enregistrement DNS externe, un enregistrement hôte A (pour IPv6, AAAA) doit exister pour le nom de domaine complet des services Web externes de votre pool frontal (par exemple, lyncwebextpool01.contoso.com).

6.  Pour un enregistrement DNS interne, dans l’arborescence de la console de votre serveur DNS, développez **zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com).
    
    <div>
    

    > [!NOTE]  
    > Si vous créez un enregistrement DNS externe, les <STRONG>zones de recherche directe</STRONG> sont déjà développées pour votre domaine SIP à l’étape 3.

    
    </div>

7.  Cliquez avec le bouton droit sur le nom de domaine SIP, puis cliquez sur **nouvel hôte (A ou AAAA)**.

8.  Dans **nom**, tapez le nom d’hôte comme suit :
    
      - Pour un enregistrement DNS interne, tapez lyncdiscoverinternal comme nom d’hôte de l’URL du service de découverte automatique interne.
    
      - Pour un enregistrement DNS externe, tapez lyncdiscover comme nom d’hôte de l’URL du service de découverte automatique externe.
    
    <div>
    

    > [!NOTE]  
    > Le nom de domaine est supposé à partir de la zone dans laquelle l’enregistrement est défini et, par conséquent, n’a pas besoin d’être entré dans le cadre de l’enregistrement A.

    
    </div>

9.  Dans **adresse IP**, tapez l’adresse IP comme suit :
    
      - Dans le cas d’un enregistrement DNS interne, tapez l’adresse IP de services Web internes du directeur (ou, si vous utilisez un équilibreur de charge, tapez l’adresse IP virtuelle de l’équilibreur de charge).
        
        <div>
        

        > [!NOTE]  
        > Si vous n’utilisez pas de réalisateur, tapez l’adresse IP du serveur frontal ou du serveur Standard Edition, ou, si vous utilisez un équilibreur de charge, tapez l’adresse IP du serveur principal de chargement.

        
        </div>
    
      - Pour un enregistrement DNS externe, tapez l’adresse IP externe ou publique du proxy inverse.

10. Cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**.

11. Pour créer un enregistrement A supplémentaires, répétez les étapes 8 à 10.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous devez créer un nouveau lyncdiscover et lyncdiscoverinternal A enregistrements dans la zone de recherche directe de chaque domaine SIP que vous prenez en charge dans votre environnement Lync Server 2013.

    
    </div>

12. Lorsque vous avez terminé de créer un (pour les enregistrements IPv6, AAAA), cliquez sur **terminé**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

