---
title: 'Lync Server 2013 : Routage de la messagerie unifiée Exchange hébergée'
TOCTitle: Routage de la messagerie unifiée Exchange hébergée
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398512(v=OCS.15)
ms:contentKeyID: 49297523
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Routage de la messagerie unifiée Exchange hébergée dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-01_

L’application de routage de messagerie unifiée Exchange s’exécute sur le serveur frontal pour acheminer les appels, soit sur un déploiement de messagerie unifiée Microsoft Exchange Server sur site, soit sur un service de messagerie unifiée Exchange hébergé.

## Application de routage ExUM

L’application de routage de messagerie unifiée ExchangeLync Server 2013 utilise les informations provenant des paramètres du compte d’utilisateur et de la stratégie de messagerie vocale hébergée pour déterminer comment acheminer les appels pour la messagerie vocale hébergée, comme illustré dans le diagramme suivant.

**Exemple de routage sur un déploiement de messagerie unifiée Exchange mixte**

![Déploiement UM Lync Server Exchange sur site](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Déploiement UM Lync Server Exchange sur site")

Le routage de messagerie unifiée Exchange peut être configuré pour acheminer les appels vers les utilisateurs activés pour la messagerie unifiée Exchange sur site, les utilisateurs activés pour la messagerie unifiée Exchange hébergée ou une combinaison des deux.

Supposons, par exemple, que la boîte aux lettres de Roy et le service de messagerie unifiée Exchange sont hébergés sur un déploiement Exchange sur site.

  - Les informations d’adresse proxy provenant du compte utilisateur de Roy indiquent que l’application de routage ExUM sert à acheminer ses appels vers un serveur de messagerie unifiée Exchange sur site.

La boîte aux lettres d’Alice et le service de messagerie unifiée Exchange sont situés sur un centre de données hébergé d’un fournisseur de services Exchange. Le routage de sa messagerie unifiée Exchange est configuré comme suit :

  - Les valeurs définies dans l’attribut msExchUCVoiceMailSettings du compte utilisateur d’Alice indiquent à l’application de routage ExUM de contrôler les informations de routage dans une stratégie de messagerie vocale hébergée.
    
    > [!NOTE]  
    > La valeur de l’attribut msExchUCVoiceMailSettings peut être définie par le fournisseur de services Exchange ou l’administrateur Lync Server 2013. Dans l’exemple illustré dans le diagramme précédent, la valeur (CsHostedVoiceMail=1) était définie par l’administrateur Lync Server 2013 pour activer la messagerie vocale hébergée pour Alice. Pour plus d’informations sur cet attribut, reportez-vous à <a href="lync-server-2013-hosted-exchange-user-management.md">Gestion des utilisateurs Exchange hébergés dans Lync Server 2013</a>.

  - La stratégie de messagerie vocale hébergée attribuée au compte utilisateur d’Alice fournit les détails de routage suivants :
    
      - La destination représente le fournisseur de services de messagerie unifiée Exchange hébergée (ls.ExUm. *\<ExchangeServerhébergé\>* .com dans cet exemple).
    
      - Les organisations sont identifiées par les ID de locataire qui sont les noms de domaine complets (FQDN) pour les messages SIP pour les locataires Exchange Server qui se trouvent sur ls.ExUm. *\<ExchangeServerhébergé\>* .com (corp.contoso.com et corp.litwareinc.com dans cet exemple).
        
        > [!NOTE]  
        > Le nom de domaine complet pour Exchange Online est exap.um.outlook.com.        
        
        
        Pour plus d’informations, reportez-vous à la section [Stratégies de messagerie vocale hébergées dans Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).

> [!NOTE]  
> Si les paramètres d’attribut msExchUCVoiceMailSettings et d’adresse proxy de messagerie unifiée sont tous deux présents dans un compte d’utilisateur, l’attribut msExchUCVoiceMailSettings est prioritaire.
