---
title: Création des enregistrements DNS pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: 'Résumé : Apprenez à configurer un serveur DNS et de créer des enregistrements DNS pour une installation de Skype pour Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 4a8374c76995a0a42aad58b54aa0d567514d07de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-dns-records-for-skype-for-business-server-2015"></a>Création des enregistrements DNS pour Skype Entreprise Server 2015
 
**Résumé :** Apprenez à configurer un serveur DNS et de créer des enregistrements DNS pour une installation de Skype pour Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise depuis le centre d’évaluation Microsoft à : [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Pour Skype pour Business Server fonctionne correctement, un certain nombre de paramètres de système de nom de domaine (DNS) doit être en place. Il s’agit afin que les clients savent comment accéder aux services et que les serveurs connaissent les uns des autres. Ces paramètres doivent être effectuées qu’une seule fois par déploiement car une fois que vous assignez une entrée DNS, il est disponible dans tout le domaine. Vous pouvez effectuer les étapes 1 à 5 dans un ordre quelconque. Cependant, vous devez exécuter les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5 comme indiqué dans le diagramme. Création d’enregistrements DNS comprend l’étape 5 de 8. Pour plus d’informations sur la planification DNS, reportez-vous à la section [exigences environnementales pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
> [!IMPORTANT]
> Il est important de remarquer qu’il ne s’agit que d’un exemple de la création d’enregistrements DNS dans un environnement Windows Server DNS. Il existe de nombreuses autres entrées DNS qui sont requises pour Skype pour le serveur de l’entreprise, et dépend de la procédure de création d’enregistrements DNS sur le système que vous utilisez pour gérer le système DNS dans votre organisation. Pour obtenir une liste complète de la configuration requise pour le serveur DNS, reportez-vous à la section [configuration DNS requise pour Skype pour Business Server 2015](../../plan-your-deployment/network-requirements/dns.md). 
  
![Schéma de vue d’ensemble](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>Configuration de DNS

Les enregistrements DNS sont requis pour Skype pour Business Server fonctionnent correctement et être accessible par les utilisateurs.
  
Cet exemple utilise un FQDN de DNS à charge équilibrée nommé pool.contoso.local. Ce pool se compose de trois serveurs exécutant Skype pour Business Server 2015, Édition entreprise. Un serveur frontal en édition Standard ne peut contenir qu’un seul serveur. En utilisant l’édition Standard, vous utilisez seulement le nom de domaine complet (FQDN) du serveur unique en édition Standard quand vous faites référence au rôle frontal au lieu de créer un pool de serveurs DNS à charge équilibrée, comme le démontre cet exemple. Cet exemple simple, qui utilise uniquement le rôle frontal, inclut les enregistrements DNS dans le tableau suivant. Pour planifier vos besoins DNS spécifiques, reportez-vous à la section [configuration DNS requise pour Skype pour Business Server 2015](../../plan-your-deployment/network-requirements/dns.md). 
  
 
|**Description**|**Type d’enregistrement**|**Nom**|**Correspond à**|**Type d’équilibrage de la charge**|
|:-----|:-----|:-----|:-----|:-----|
|Nom de domaine complet des services web internes  <br/> |A  <br/> |webint.contoso.local  <br/> |VIP pour les services web internes  <br/> |Logiciel et matériel pris en charge  <br/> |
|FQDN du pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Adresse IP du serveur SFB01  <br/> |DNS  <br/> |
|FQDN SFB01  <br/> |A  <br/> |SFB01.contoso.local  <br/> |Adresse IP du serveur SFB01  <br/> |DNS  <br/> |
|FQDN du pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Adresse IP du serveur SFB02  <br/> |DNS  <br/> |
|FQDN SFB02  <br/> |A  <br/> |SFB02.contoso.local  <br/> |Adresse IP du serveur SFB02  <br/> |DNS  <br/> |
|FQDN du pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Adresse IP du serveur SFB03  <br/> |DNS  <br/> |
|FQDN SFB03  <br/> |A  <br/> |SFB03.contoso.local  <br/> |Adresse IP du serveur SFB03  <br/> |DNS  <br/> |
|Fonction de découverte automatique de Skype Entreprise  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |VIP pour les services web internes  <br/> |Logiciel et matériel pris en charge  <br/> |
|URL simple de réunion  <br/> |A  <br/> |Meet.contoso.local  <br/> |VIP pour les services web internes  <br/> |Logiciel et matériel pris en charge  <br/> |
|URL simple Dial-in  <br/> |A  <br/> |Dialin.contoso.local  <br/> |VIP pour les services web internes  <br/> |Logiciel et matériel pris en charge  <br/> |
|URL simple de Web Scheduler  <br/> |A  <br/> |Scheduler.contoso.local  <br/> |VIP pour les services web internes  <br/> |Logiciel et matériel pris en charge  <br/> |
|URL simple d’administration  <br/> |A  <br/> |Admin.contoso.local  <br/> |VIP pour les services web internes  <br/> |Logiciel et matériel pris en charge  <br/> |
|Découverte d’élément hérité  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |FQDN du pool (port 5061)  <br/> |N/A  <br/> |
   
### <a name="create-dns-records"></a>Créer des enregistrements DNS

1. Connectez-vous au serveur DNS et ouvrez le **Gestionnaire de serveur**.
    
2. Cliquez sur le menu déroulant **Outils**, puis sur **DNS**.
    
3. Dans l’arborescence de la console pour votre domaine SIP, développez **Zones de recherche directes**, puis développez le domaine SIP dans lequel Skype pour Business Server va être installé.
    
4. Cliquez avec le bouton droit sur le domaine SIP et sélectionnez **Nouvel hôte (A ou AAAA)**, comme indiqué dans la figure.
    
     ![Sélection d’un nouvel enregistrement A](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. Dans la zone **Nom**, tapez le nom de l’enregistrement de l’hôte (le nom du domaine est automatiquement ajouté).
    
6. Dans la zone **Adresse IP**, saisissez l’adresse IP du serveur frontal individuel, puis sélectionnez **Créer un enregistrement de pointeur associé (PTR)** ou **Autoriser tout utilisateur identifié à mettre à jour les enregistrements DNS avec le même nom de propriétaire**, le cas échéant. Veuillez remarquer qu’il est supposé que DNS est utilisé pour équilibrer la charge de tout le trafic, à l’exception des services web. Dans cet exemple, nous avons trois serveurs frontaux, comme indiqué dans le tableau.
    
   |**Nom du serveur**|**Type de**|**Données**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |Hôte (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |Hôte (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |Hôte (A)  <br/> |10.0.0.7  <br/> |
   
7. Ensuite, créez les entrées d’équilibrage de charge DNS pour le pool. L’équilibrage de charge DNS permet à DNS d’envoyer des demandes aux serveurs individuels du pool en utilisant le même nom de pool DNS. Pour plus d’informations sur DNS et l’équilibrage de charge, consultez la [configuration DNS requise pour Skype pour Business Server 2015](../../plan-your-deployment/network-requirements/dns.md). 
    
    > [!NOTE]
    > La mise en pool de plusieurs serveurs est possible seulement dans les déploiements de l’édition Enterprise. Si vous déployez un serveur Enterprise unique ou un serveur en édition Standard, il vous suffit de créer un enregistrement A pour le serveur unique. 
  
    Par exemple, pour un pool nommé pool.contoso.local avec trois serveurs frontaux, vous devrez créer les entrées DNS suivantes :
    
   |**NOM DE DOMAINE COMPLET**|**Type de**|**Données**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |Hôte (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |Hôte (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |Hôte (A)  <br/> |10.0.0.7  <br/> |
   
8. Continuez à créer des enregistrements A pour tous les serveurs du déploiement prévu. 
    
9. Pour créer l’enregistrement de service SRV pour la découverte d’éléments hérités, cliquez avec le bouton droit sur le domaine SIP et sélectionnez **Nouveaux enregistrements**.
    
10. Dans **Choisissez un type d’enregistrement de ressource**, cliquez sur **Emplacement du service (SRV)**, puis sur **Créer un enregistrement**.
    
11. Cliquez sur **Service**, puis tapez **_sipinternaltls**.
    
12. Cliquez sur **Protocole**, puis tapez **_tcp**.
    
13. Cliquez sur **Numéro de port**, puis saisissez **5061**.
    
14. Cliquez sur **Hôte offrant ce service**, puis tapez le nom de domaine complet du pool ou du serveur en édition Standard.
    
     ![Capture d’écran de la boîte de dialogue du nouvel enregistrement de ressource.](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. Cliquez sur **OK**, puis sur **Terminé**.
    
### <a name="verify-dns-records"></a>Vérification d’enregistrements DNS

1. Ouvrez une session sur un ordinateur client du domaine dont le compte est membre du groupe Utilisateurs authentifiés ou qui dispose des autorisations équivalentes.
    
2. Cliquez sur **Démarrer**, puis saisissez **cmd** et appuyez sur Entrée.
    
3. Type de **nslookup \<nom de domaine complet du pool frontal de\> ** ou ** \<nom de domaine complet du serveur Standard Edition ou serveur Enterprise Edition\>**, puis appuyez sur ENTRÉE.
    
4. Continuez à vérifier le reste des enregistrements A pour votre déploiement.
    
5. Si vous prenez en charge les clients hérités et si vous avez créé l’enregistrement SRV, vérifiez-le en saisissant **set type=srv** à l’invite **nslookup**, puis appuyez sur Entrée.
    
6. Type ** _sipinternaltls._tcp. *domaine* ** (par exemple, _sipinternaltls._tcp.contoso.local), puis appuyez sur ENTRÉE.
    
7. Le résultat prévu devrait ressembler au résultat affiché dans la figure. Veuillez remarquer que, bien que tous les enregistrements DNS ne soient pas affichés dans la sortie, il faut vérifier tous les enregistrements. 
    
     ![Vérifiez les paramètres DNS.](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

