---
title: Configuration du DNS pour la découverte automatique
TOCTitle: Configuration du DNS pour la découverte automatique
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945656(v=OCS.15)
ms:contentKeyID: 53095559
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du DNS pour la découverte automatique

 

_**Dernière rubrique modifiée :** 2012-12-12_

Pour prendre en charge la découverte automatique pour les clients de Lync, vous devez créer les enregistrements DNS (Domain Name System) suivants :

  - un enregistrement DNS interne afin de prendre en charge les clients Lync qui se connectent depuis le réseau de votre organisation ;

  - un enregistrement DNS externe, ou public, afin de prendre en charge les clients Lync qui se connectent depuis Internet.

Vous devez créer un enregistrement DNS interne et un enregistrement DNS externe pour chaque domaine SIP.

Les enregistrements DNS peuvent être des enregistrements A (hôte) ou des enregistrements CNAME en fonction de la capacité à créer de nouveaux certificats avec d’autres noms d’objet (SAN). Si vous n’êtes pas en mesure de demander et de déployer un nouveau certificat (public) externe avec le lyncdiscover.\<nom\_domaine\> SAN, utilisez la procédure pour utiliser le port HTTP/TCP 80. Les procédures suivantes décrivent comment créer des enregistrements DNS internes et externes.

## Pour créer des enregistrements CNAME DNS

1.  Ouvrez une session sur un serveur DNS comme suit :
    
      - Pour créer un enregistrement DNS interne, ouvrez une session sur un serveur DNS de votre réseau en tant que membre du groupe Administrateurs du domaine ou DnsAdmins.
    
      - Pour créer un enregistrement DNS externe, connectez-vous à votre fournisseur DNS public.

2.  Ouvrez le composant logiciel enfichable DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

3.  Effectuez l’une des opérations suivantes :
    
      - Pour un enregistrement DNS interne, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine Active Directory (par exemple, contoso.local).
        
        > [!NOTE]  
        > Il s’agit du domaine Active Directory dans lequel sont installés votre pool de directeurLync Server 2013 et le pool de serveurs frontaux.    
      - Pour un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).

4.  Vérifiez qu’il existe un enregistrement A d’hôte pour votre pool de directeurs comme suit :
    
      - Pour un enregistrement DNS interne, il doit exister un enregistrement A d’hôte pour le nom de domaine complet des services web internes pour votre pool de directeurs (par exemple, lyncwebdir01.contoso.local).
    
      - Pour un enregistrement DNS externe, il doit exister un enregistrement A d’hôte pour le nom de domaine complet des services web externes pour votre pool de directeurs (par exemple, lyncwebextdir.contoso.com).

5.  Vérifiez qu’il existe un enregistrement A d’hôte pour votre pool de serveurs frontaux comme suit :
    
      - Pour un enregistrement DNS interne, il doit exister un enregistrement A d’hôte pour le nom de domaine complet des services web internes pour votre pool de serveurs frontaux (par exemple, lyncwebpool01.contoso.local).
    
      - Pour un enregistrement DNS externe, il doit exister un enregistrement A d’hôte pour le nom de domaine complet des services web externes pour votre pool de serveurs frontaux (par exemple, lyncwebextpool01.contoso.com).

6.  Pour un enregistrement DNS interne, dans l’arborescence de la console de votre serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).
    
    > [!NOTE]  
    > Si vous créez un enregistrement DNS externe, <strong>Zones de recherche directes</strong> est déjà développé pour votre domaine SIP (suite à l’étape 3).

7.  Cliquez avec le bouton droit sur le nom du domaine SIP, puis cliquez sur **Nouvel alias (CNAME)**.

8.  Dans **Nom de l’alias**, tapez l’un des éléments suivants :
    
      - Pour un enregistrement DNS interne, tapez lyncdiscoverinternal comme nom d’hôte pour l’URL du service de découverte automatique interne.
    
      - Pour un enregistrement DNS externe, tapez lyncdiscover comme nom d’hôte pour l’URL du service de découverte automatique externe.

9.  Dans **Nom de domaine complet (FQDN) pour l’hôte de destination**, effectuez l’une des opérations suivantes :
    
      - Pour un enregistrement DNS interne, tapez ou naviguez jusqu’au nom de domaine complet des services web internes de votre pool de directeurs (par exemple, lyncwebdir01.contoso.local), puis cliquez sur **OK**.
    
      - Pour un enregistrement DNS externe, tapez ou naviguez jusqu’au nom de domaine complet des services web externes de votre pool de directeurs (par exemple, lyncwebextdir.contoso.com), puis cliquez sur **OK**.
    
    > [!NOTE]  
    > Si vous n’utilisez pas de directeur, utilisez le nom de domaine complet des services web interne et externe de votre pool de serveurs frontaux, ou, pour un serveur unique, le nom de domaine complet du serveur frontal ou serveur Standard Edition. 
       
    > [!IMPORTANT]  
    > Vous devez créer un enregistrement CNAME de découverte automatique dans la zone de recherche directe de chaque domaine SIP que vous prenez en charge dans votre environnement Lync Server 2013.

## Pour créer des enregistrements A DNS

1.  Ouvrez une session sur un serveur DNS comme suit :
    
      - Pour créer un enregistrement DNS interne, ouvrez une session sur un serveur DNS de votre réseau en tant que membre du groupe Administrateurs du domaine ou DnsAdmins.
    
      - Pour créer un enregistrement DNS externe, connectez-vous à votre fournisseur DNS public ou serveur DNS externe.

2.  Ouvrez le composant logiciel enfichable DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

3.  Effectuez l’une des opérations suivantes :
    
      - Pour un enregistrement DNS interne, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine Active Directory (par exemple, contoso.local).
        
        > [!NOTE]  
        > Il s’agit du domaine Active Directory dans lequel sont installés votre pool de directeurLync Server 2013 et le pool de serveurs frontaux.    
      - Pour un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).

4.  Vérifiez qu’il existe un enregistrement A (AAAA pour IPv6) d’hôte pour votre pool de directeurs comme suit :
    
      - Pour un enregistrement DNS interne, il doit exister un enregistrement A (AAAA pour IPv6) d’hôte pour le nom de domaine complet des services web internes pour votre pool de directeurs (par exemple, lyncwebdir01.contoso.local).
    
      - Pour un enregistrement DNS externe, il doit exister un enregistrement A (AAAA pour IPv6) d’hôte pour le nom de domaine complet des services web externes pour votre pool de directeurs (par exemple, lyncwebextdir.contoso.com).

5.  Vérifiez qu’il existe un enregistrement A (AAAA pour IPv6) d’hôte pour votre pool de serveurs frontaux comme suit :
    
      - Pour un enregistrement DNS interne, il doit exister un enregistrement A (AAAA pour IPv6) d’hôte pour le nom de domaine complet des services web internes pour votre pool de serveurs frontaux (par exemple, lyncwebpool01.contoso.local).
    
      - Pour un enregistrement DNS externe, il doit exister un enregistrement A (AAAA pour IPv6) d’hôte pour le nom de domaine complet des services web externes pour votre pool de serveurs frontaux (par exemple, lyncwebextpool01.contoso.com).

6.  Pour un enregistrement DNS interne, dans l’arborescence de la console de votre serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).
    
    > [!NOTE]  
    > Si vous créez un enregistrement DNS externe, <strong>Zones de recherche directes</strong> est déjà développé pour votre domaine SIP (suite à l’étape 3).

7.  Cliquez avec le bouton droit sur le nom du domaine SIP, puis cliquez sur **Nouvel hôte (A ou AAAA)**.

8.  Dans **Nom**, tapez le nom d’hôte comme suit :
    
      - Pour un enregistrement DNS interne, tapez lyncdiscoverinternal comme nom d’hôte pour l’URL du service de découverte automatique interne.
    
      - Pour un enregistrement DNS externe, tapez lyncdiscover comme nom d’hôte pour l’URL du service de découverte automatique externe.
    
    > [!NOTE]  
    > Le nom de domaine est déduit d’après la zone dans laquelle l’enregistrement est défini ; il est par conséquent inutile de l’entrer dans le cadre de l’enregistrement A.

9.  Dans **Adresse IP**, tapez l’adresse IP comme suit :
    
      - Pour un enregistrement DNS interne, tapez l’adresse IP interne des services web du directeur (ou, si vous utilisez un équilibrage de la charge, tapez l’adresse IP virtuelle (VIP) de l’équilibrage de charge du directeur).
        
        > [!NOTE]  
        > Si vous n’utilisez pas de directeur, tapez l’adresse IP du serveur frontal ou du serveur Standard Edition ou, si vous utilisez un équilibrage de la charge, tapez l’adresse IP de l’équilibrage de charge pool de serveurs frontaux.    
      - Pour un enregistrement DNS externe, tapez l’adresse IP externe ou publique du proxy inverse.

10. Cliquez sur **Ajouter un hôte**, puis sur **OK**.

11. Pour créer un enregistrement A supplémentaire, répétez les étapes 8 à 10.
    
    > [!IMPORTANT]  
    > Vous devez créer des enregistrements A lyncdiscover et lyncdiscoverinternal dans la zone de recherche directe de chaque domaine SIP que vous prenez en charge dans votre environnement Lync Server 2013.

12. Lorsque vous avez terminé de créer des enregistrements A (AAAA pour IPv6), cliquez sur **Terminé**.

