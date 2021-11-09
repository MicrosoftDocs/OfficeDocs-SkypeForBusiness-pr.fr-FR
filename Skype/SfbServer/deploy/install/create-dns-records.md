---
title: Créer des enregistrements DNS pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: "Résumé : Découvrez comment configurer DNS et créer des enregistrements DNS pour une installation de Skype Entreprise Server. Téléchargez une version d’évaluation Skype Entreprise Server gratuite à partir du Centre d’évaluation Microsoft à https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server l':."
ms.openlocfilehash: 177568623148b64b3dccd885e2e7ff3740149c62
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850367"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>Créer des enregistrements DNS pour Skype Entreprise Server
 
**Résumé :** Découvrez comment configurer DNS et créer des enregistrements DNS pour une installation de Skype Entreprise Server. Téléchargez une version d’Skype Entreprise Server gratuite à partir du Centre d’évaluation Microsoft à [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) l':.
  
Pour Skype Entreprise Server fonctionne correctement, un certain nombre de paramètres DNS (Domain Name System) doivent être en place. Cela afin que les clients sachent comment accéder aux services et que les serveurs se connaissent mutuellement. Ces paramètres ne doivent être remplis qu’une seule fois par déploiement, car une fois que vous avez attribué une entrée DNS, elle est disponible dans l’ensemble du domaine. Vous pouvez suivre les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez suivre les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5, comme indiqué dans le diagramme. La création d’enregistrements DNS comprend l’étape 5 sur 8. Pour plus d’informations sur la planification du DNS, voir [Environmental requirements for Skype Entreprise Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server requirements for Skype Entreprise Server [2019](../../../SfBServer2019/plan/system-requirements.md).
  
> [!IMPORTANT]
> Il est important de noter qu’il s’agit simplement d’un exemple de création d’enregistrements DNS dans un environnement DNS Windows Server. De nombreuses autres entrées DNS sont requises pour Skype Entreprise Server, et la procédure de création des enregistrements DNS dépend du système que vous utilisez pour gérer le DNS dans votre organisation. Pour obtenir la liste complète des conditions requises pour le DNS, consultez la liste des exigences [DNS pour Skype Entreprise Server](../../plan-your-deployment/network-requirements/dns.md). 
  
![Diagramme de vue d’ensemble.](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>Configurer le DNS

Les enregistrements DNS sont requis pour Skype Entreprise Server fonctionnent correctement et soient accessibles par les utilisateurs.
  
Cet exemple utilise un FQDN avec charge DNS équilibrée nommé pool.contoso.local. Ce pool se compose de trois serveurs exécutant Skype Entreprise Server Êdition Entreprise. Un Édition Standard frontal ne peut contenir qu’un seul serveur. À l’aide de Édition Standard, vous utilisez uniquement le nom de domaine complet (FQDN) du serveur Édition Standard unique lors du référencement du rôle frontal au lieu de créer un pool de serveurs d’équilibrage de charge DNS, comme le montre cet exemple. Cet exemple simple qui utilise uniquement le rôle frontal inclut les entrées DNS du tableau suivant. Pour planifier vos besoins DNS spécifiques, consultez les exigences [DNS pour Skype Entreprise Server](../../plan-your-deployment/network-requirements/dns.md). 
  
 
|**Description**|**Type d’enregistrement**|**Name**|**Résolu en**|**Type d’équilibrage de charge**|
|:-----|:-----|:-----|:-----|:-----|
|FQDN des services web internes  <br/> |A  <br/> |webint.contoso.local  <br/> |ADRESSE VIP pour les services web internes  <br/> |Logiciels et matériels pris en charge  <br/> |
|Nom de domaine complet du pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Adresse IP du serveur SFB01  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |Adresse IP du serveur SFB01  <br/> |DNS  <br/> |
|Nom de domaine complet du pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Adresse IP du serveur SFB02  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02.contoso.local  <br/> |Adresse IP du serveur SFB02  <br/> |DNS  <br/> |
|Nom de domaine complet du pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Adresse IP du serveur SFB03  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03.contoso.local  <br/> |Adresse IP du serveur SFB03  <br/> |DNS  <br/> |
|Skype Entreprise Découverte automatique  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |ADRESSE VIP pour les services web internes  <br/> |Logiciels et matériels pris en charge  <br/> |
|URL simple de réunion  <br/> |A  <br/> |meet.contoso.local  <br/> |ADRESSE VIP pour les services web internes  <br/> |Logiciels et matériels pris en charge  <br/> |
|URL simple de numérotation  <br/> |A  <br/> |dialin.contoso.local  <br/> |ADRESSE VIP pour les services web internes  <br/> |Logiciels et matériels pris en charge  <br/> |
|URL simple du Programmeur Web  <br/> |A  <br/> |scheduler.contoso.local  <br/> |ADRESSE VIP pour les services web internes  <br/> |Logiciels et matériels pris en charge  <br/> |
|URL simple d’administration  <br/> |A  <br/> |admin.contoso.local  <br/> |ADRESSE VIP pour les services web internes  <br/> |Logiciels et matériels pris en charge  <br/> |
|Découverte héritée  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |FQDN du pool (port 5061)  <br/> |S/O  <br/> |
   
### <a name="create-dns-records"></a>Créer des enregistrements DNS

1. Connectez-vous au serveur DNS et ouvrez le **Gestionnaire de serveur.**
    
2. Cliquez sur **le** menu déroulant Outils, puis sur **DNS**.
    
3. Dans l’arborescence de la console pour votre domaine SIP, développez **zones** de recherche avant, puis développez le domaine SIP dans lequel Skype Entreprise Server sera installé.
    
4. Cliquez avec le bouton droit sur le domaine SIP, puis sélectionnez Nouvel hôte **(A ou AAAA),** comme illustré dans la figure.
    
     ![sélection d’un nouvel enregistrement A.](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. Dans la **zone** Nom, tapez le nom de l’enregistrement hôte (le nom de domaine sera automatiquement ajouté).
    
6. Dans la zone Adresse **IP,** tapez l’adresse IP du serveur frontal individuel, puis sélectionnez Créer un enregistrement de **pointeur associé (PTR)** ou autoriser tout utilisateur authentifié à mettre à jour les enregistrements **DNS** avec le même nom de propriétaire, le cas échéant. Notez que cela suppose que le DNS est utilisé pour équilibrer la charge de tout le trafic à l’exception des services web. Dans cet exemple, nous avons trois serveurs frontux, comme indiqué dans le tableau.
    
   |**Nom du serveur**|**Type**|**Données**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |Hôte (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |Hôte (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |Hôte (A)  <br/> |10.0.0.7  <br/> |
   
7. Ensuite, créez les entrées d’équilibrage de charge DNS pour le pool. L’équilibrage de charge DNS permet au DNS d’envoyer des demandes aux serveurs individuels du pool tout en utilisant le même nom de pool DNS. Pour plus d’informations sur le DNS et l’équilibrage de charge, voir [la](../../plan-your-deployment/network-requirements/dns.md)Skype Entreprise Server . 
    
    > [!NOTE]
    > La mise en pool de plusieurs serveurs est disponible uniquement dans Êdition Entreprise déploiements. Si vous déployez un serveur Enterprise ou un serveur Édition Standard, vous devez créer uniquement un enregistrement A pour le serveur unique. 
  
    Par exemple, si vous avez un pool nommé pool.contoso.local et trois serveurs frontaux, vous devez créer les entrées DNS suivantes :
    
   |**FQDN**|**Type**|**Données**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |Hôte (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |Hôte (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |Hôte (A)  <br/> |10.0.0.7  <br/> |
   
8. Continuez à créer des enregistrements A pour tous les serveurs dans le déploiement planifié. 
    
9. Pour créer l’enregistrement de service (SRV) pour la découverte héritée, cliquez avec le bouton droit sur le domaine SIP, puis sélectionnez **Autres nouveaux enregistrements.**
    
10. Dans **Choisissez un type d’enregistrement de ressource**, cliquez sur **Emplacement du service (SRV)**, puis sur **Créer un enregistrement**.
    
11. Cliquez sur **Service**, puis tapez **_sipinternaltls**.
    
12. Cliquez sur **Protocole**, puis tapez **_tcp**.
    
13. Cliquez sur **Numéro de port**, puis tapez **5061**.
    
14. Cliquez **sur Hôte offrant ce service,** puis tapez le nom de Édition Standard serveur.
    
     ![Capture d’écran de la boîte de dialogue nouvel enregistrement de ressource.](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. Cliquez sur **OK**, puis sur **Terminé**.
    
### <a name="verify-dns-records"></a>Vérifier les enregistrements DNS

1. Ouvrez une session sur un ordinateur client du domaine dont le compte est membre du groupe Utilisateurs authentifiés ou qui dispose des autorisations équivalentes.
    
2. Cliquez **sur** Démarrer, puis **tapez cmd,** puis appuyez sur Entrée.
    
3. Tapez **nslookup ou \<FQDN of the Front End pool\>** , puis **\<FQDN of the Standard Edition server or single Enterprise Edition server\>** appuyez sur Entrée.
    
4. Continuez à vérifier le reste des enregistrements A pour votre déploiement.
    
5. Si vous prisez en charge les clients hérités et que vous avez créé l’enregistrement SRV, vérifiez-le en tapant **set type=srv** à l’invite **nslookup,** puis appuyez sur Entrée.
    
6. Tapez **_sipinternaltls._tcp. *domain*** (par exemple, _sipinternaltls._tcp.contoso.local), puis appuyez sur Entrée.
    
7. La sortie attendue doit être similaire à celle indiquée dans la figure. Notez que tous les enregistrements DNS ne sont pas affichés dans l’exemple de sortie, mais que tous les enregistrements doivent être vérifiés. 
    
     ![Vérifiez les paramètres dns.](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

