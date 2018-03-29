---
title: Notions de base sur DNS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 dispose d’un logiciel intégré qui peut fournir des services DNS, il est conseillé de consulter la documentation disponible, par exemple le Guide de scénario de stratégie DNS. Vous pouvez choisir une solution tierce si vous le souhaitez.
ms.openlocfilehash: df6a693c50b3ca8b61baf0e47e0d019478f3cbf9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="dns-basics"></a>Notions de base sur DNS
 
Windows Server 2016 dispose d’un logiciel intégré qui peut fournir des services DNS, afin que vous souhaiterez peut-être consulter la documentation disponible par exemple le [Guide de scénario de stratégie DNS](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/dns-policy-scenario-guide). Vous pouvez choisir une solution tierce si vous le souhaitez.
  
Nous vous recommandons des meilleurs dédier un serveur spécifique dans votre implémentation de fournir au système DNS. Vous pouvez éventuellement configurer il sur l’un des serveurs dédiés à l’une de la Skype pour les rôles serveur d’entreprise, mais si ce serveur fait également partie d’un pool et s’il a été mis hors service par accident Skype pour entreprise serait mal fonctionner jusqu'à ce que les services DNS ont été rétablies.
  
## <a name="dns-records"></a>Enregistrements DNS

Chaque mappage d’un nom à une adresse IP (et qui peut être une adresse IPv4 ou IPv6) sont stockées dans un enregistrement DNS sur le serveur DNS. Le nom est décrite dans le rapport de DNS spécifiquement sous la forme d’un nom de domaine complet, un nom de domaine complet. *Contoso.com* est un nom de domaine valide, elle est l’abréviation de * \*. contoso.com* , donc il est ambigu et éventuellement peut désigner n’importe quel serveur dans le domaine. Un exemple de nom de domaine complet qui fait référence à un seul serveur dans votre domaine peut être **meeting01.contoso.com**.
  
> [!IMPORTANT]
> Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom d’hôte, et non un nom de domaine complet. Générateur de topologies utilise des noms de domaine complets, pas les noms d’hôte. Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur à déployer en tant que serveur Edge non joint à un domaine. **Utilisez des caractères standard uniquement** (y compris les A-Z, a-z, 0-9 et des traits d’union) lors de l’attribution de noms de domaine complets de vos serveurs exécutant Skype pour Business Server. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans les noms de domaine complets ne sont généralement pas pris en charge par les systèmes DNS externes et les autorités publiques de certification (lorsque le nom de domaine complet doit être affecté à l’élément SN (Subject Name) du certificat).
  
En plus d’une adresse IP, le nom de domaine complet peut être mappé à une **adresse IP virtuelle** , une adresse IP virtuelle. Une adresse VIP est une adresse IP qui ne correspond pas à une interface réseau physique. Souvent, une adresse VIP pointe vers un pool de serveurs jouant un rôle de serveur, ou à une paire de serveurs configurés pour la redondance et la tolérance de panne.
  
Il existe plusieurs types d’enregistrement DNS, ceux qui est les plus pertinentes pour cette discussion : 
  
- **A** — un enregistrement d’adresse ou d’un enregistrement d’hôte, renvoie une adresse IPv4 de 32 bits. La plupart du temps utilisé pour mapper les noms d’hôte à une adresse IP de l’hôte.
    
- **AAAA** : un enregistrement d’adresse IPv6. Renvoie une adresse IPv6 de 128 bits. La plupart du temps utilisé pour mapper les noms d’hôte à une adresse IP de l’hôte.
    
- **CNAME** , un enregistrement de nom canonique. Cela résout un nom à un autre : la recherche DNS essaiera à nouveau la recherche avec un nouveau nom.
    
- **SRV** : un enregistrement de Service (enregistrements SRV) spécifie un service qui est accessible sur un port spécifique et une combinaison IP (il s’agit d’un processus sur un serveur). Les noms des services nécessitant un enregistrement de service sont fixes et ne peuvent pas être personnalisées au-delà de ce qui les rend une partie de votre domaine SIP. Certains services d’utilisateur utilisent une URL Simple. Un enregistrement SRV doit pointer vers un emplacement dans le même domaine SIP, donc si vous avez plusieurs domaines, vous devez plusieurs enregistrements SRV pour un service donné.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Comment choisir un nom de domaine SIP
<a name="BK_NameSIP"> </a>

Nom de domaine d’une organisation SIP s’aligne généralement avec les adresses de messagerie tenus ses utilisateurs. Si un utilisateur de votre organisation doit recevoir une adresse de messagerie comme Brown@contoso.com, le préféré \<-domaine sip\> pour une organisation avec le domaine contoso.com, le nom est simplement de contoso.com.
  
### <a name="multiple-sip-domains"></a>Plusieurs domaines SIP

 Votre organisation peut, dans certains cas, avoir plusieurs domaines SIP. Par exemple, si Fabrikam.com a été acquis par contoso.com, vous devrez créer un nouveau domaine SIP Skype pour Business Server reconnaît et accepte la connexion à partir de. Lorsque vous effectuez cette opération, vous devez créer un jeu supplémentaire de tous les enregistrements DNS qui utilisent contoso.com, avec les nouveaux noms de domaine complets qui montrent où envoyer les demandes de Fabrikam.
  
## <a name="dns-load-balancing"></a>Équilibrage de charge DNS
<a name="BK_NameSIP"> </a>

Vous pouvez utiliser DNS pour partager la charge du trafic entre plusieurs serveurs sont paramétrés comme un pool de serveurs. Pour ce faire, vous créez plusieurs enregistrements A pour nom de domaine complet du pool, chacun d’eux pointe vers l’adresse IP d’un nœud dans le pool.
  
Pour plus d’informations de l’équilibrage de charge, consultez [DNS de l’équilibrage de la charge](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) .
  

