---
title: Menaces de sécurité courantes dans l’informatique moderne
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/22/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
description: Comme Skype Entreprise Server est un système de communication de classe entreprise, vous devez être conscient des attaques de sécurité courantes qui peuvent affecter son infrastructure et ses communications.
ms.openlocfilehash: dcc889ea43c06c2f8166d588b8d7e5eb7075b52c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741920"
---
# <a name="common-security-threats-in-modern-day-computing"></a>Menaces de sécurité courantes dans l’informatique moderne
 
Comme Skype Entreprise Server est un système de communication de classe entreprise, vous devez être conscient des attaques de sécurité courantes qui peuvent affecter son infrastructure et ses communications.
  
## <a name="compromised-key-attack"></a>Attaque par clé compromise

Une clé est un code ou un nombre secret utilisé pour chiffrer, déchiffrer ou valider des informations confidentielles. Deux clés sensibles sont en cours d’utilisation dans l’infrastructure à clé publique (PKI) qui doivent être considérées : 
  
- Clé privée de chaque titulaire du certificat
    
- Clé de session utilisée après un échange réussi de clés d’identification et de session par les partenaires communiquants
    
Une attaque par clé compromise se produit lorsque l’intrus détermine la clé privée ou la clé de session. Lorsque l’intrus parvient à déterminer la clé, il s’en sert pour déchiffrer des données chiffrées, à l’insu de l’expéditeur des données.
  
Skype Entreprise Server utilise les fonctionnalités pKI du système d’exploitation Windows Server pour protéger les données de clé utilisées pour le chiffrement des connexions TLS (Transport Layer Security). Les clés utilisées pour le chiffrement multimédia sont échangées sur des connexions TLS.
  
## <a name="network-denial-of-service-attack"></a>Attaque réseau par déni de service

Une attaque par déni de service se produit lorsqu’une personne malveillante empêche des utilisateurs valides de travailler et d’utiliser le réseau normalement. Cette fonction est effectuée lorsque l’attaquant inonde le service de demandes légitimes qui submergent l’utilisation du service par des utilisateurs légitimes. En utilisant une attaque par déni de service, l’attaquant peut :
  
- envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;
    
- envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;
    
- masquer les signes d’attaque ;
    
- empêcher les utilisateurs d’accéder aux ressources réseau.
    
## <a name="eavesdropping-sniffing-snooping"></a>Écoute (renifleur, snooping)

Une attaque par écoute peut se produire lorsqu’une personne malveillante parvient à accéder au chemin d’accès des données d’un réseau et qu’elle peut ainsi surveiller et lire le trafic. Cette attaque est également appelée reniflage (« sniffing ») ou surveillance (« snooping »). Si le trafic consiste en du texte simple, l’intrus peut lire le trafic lorsqu’il accède au chemin d’accès des données. Par exemple, une attaque peut être lancée en contrôlant un routeur sur le chemin de données. 
  
La recommandation par défaut et le paramètre pour le trafic au sein de Skype Entreprise Server consiste à utiliser Mutual TLS (MTLS) entre les serveurs de confiance et TLS du client au serveur. Cette mesure de protection rendrait une attaque très difficile ou impossible à réaliser pendant la période pendant laquelle une conversation donnée se produit. TLS authentifie toutes les parties et crypte tout le trafic. Cela n’empêche pas l’écoute clandestine, mais l’attaquant ne peut pas lire le trafic, sauf si le chiffrement est rompu.
  
Le protocole TURN (Traversal Using Relay NAT) n’a pas pour mission de chiffrer le trafic et les informations qu’il envoie sont protégées par l’intégrité des messages. Bien qu’il soit ouvert à l’écoute clandestine, les informations qu’il envoie (c’est-à-dire les adresses IP et le port) peuvent être extraites directement en regardant simplement les adresses source et de destination des paquets. Le service Edge A/V garantit que les données sont valides en vérifiant l’intégrité des messages du message à l’aide de la clé dérivée de quelques éléments, y compris un mot de passe TURN, qui n’est jamais envoyé en texte clair. Si le protocole SRTP (Secure Real Time Protocol) est utilisé, le trafic multimédia est également chiffré.
  
## <a name="identity-spoofing-ip-address-and-caller-id-spoofing"></a>Usurpation d’identité (usurpation d’adresse IP et ID d’appelant)

L’usurpation d’identité se produit lorsque l’attaquant détermine et utilise un numéro de téléphone d’un utilisateur valide (ID d’appelant) ou une adresse IP d’un réseau, d’un ordinateur ou d’un composant réseau sans être autorisé à le faire. Une attaque réussie permet à l’attaquant de fonctionner comme s’il s’agit de l’entité normalement identifiée par le numéro de téléphone (ID de l’appelant) ou l’adresse IP.

Dans le contexte du Skype Entreprise Server, l’usurpation d’adresse IP n’entre en jeu que si un administrateur a effectué les deux choses suivantes :
  
- Connexions configurées qui ne supportent que le protocole TCP (Transmission Control Protocol) (ce qui n’est pas recommandé, car les communications TCP ne sont pas chiffrées).
    
- Marqué les adresses IP de ces connexions comme hôtes de confiance.
    
Il s’agit moins d’un problème pour les connexions TLS (Transport Layer Security), car TLS authentifier toutes les parties et chiffre tout le trafic. L’utilisation de TLS empêche un attaquant d’effectuer une usurpation d’adresse IP sur une connexion spécifique (par exemple, des connexions TLS mutuelles). Toutefois, un attaquant peut toujours usurper l’adresse du serveur DNS qu’Skype Entreprise Server utilise. Toutefois, étant donné que l’authentification dans Skype Entreprise est effectuée avec des certificats, une personne malveillante ne doit pas avoir de certificat valide pour usurper l’identité de l’une des parties dans la communication.

En revanche, l’usurpation d’ID d’appelant entre en jeu lorsque vous avez établi une trunk SIP entre un fournisseur, une passerelle PSTN ou un autre système PBX et Skype Entreprise Server. Dans ce cas, Skype Entreprise Server n’offre aucune protection contre l’usurpation d’ID d’appelant. Cela signifie qu’un utilisateur Skype Entreprise peut recevoir un appel à partir de la ligne SIP avec un ID d’appelant usurpé affichant le numéro de téléphone ou le nom complet (si la recherche de numéro inversée s’applique) d’un autre Skype Entreprise utilisateur. La protection doit être appliquée côté fournisseur, PSTN ou passerelle PBX.
  
## <a name="man-in-the-middle-attack"></a>Man-in-the-Middle Attack

Une attaque de l’intermédiaire se produit lorsqu’une personne malveillante redirige la communication entre deux utilisateurs via l’ordinateur de l’attaquant à l’insu des deux utilisateurs en communication. L’attaquant peut surveiller et lire le trafic avant de l’envoyer au destinataire prévu. Chaque utilisateur de la communication envoie sans le savoir le trafic vers et reçoit le trafic de l’attaquant, tout en pensez qu’il communique uniquement avec l’utilisateur prévu. Cela peut se produire si une personne malveillante peut modifier les services de domaine Active Directory pour ajouter son serveur en tant que serveur approuvé ou modifier le DNS (Domain Name System) pour que les clients se connectent via l’attaquant lors de leur accès au serveur. Une attaque de l’intermédiaire peut également se produire avec le trafic multimédia entre deux clients. Toutefois Skype Entreprise Server, dans le partage audio, vidéo et d’application de point à point, les flux sont chiffrés avec SRTP, à l’aide de clés de chiffrement négociées entre les homologues qui utilisent le protocole SIP (Session Initiation Protocol) sur TLS. Les serveurs tels que la conversation de groupe utilisent HTTPS pour améliorer la sécurité du trafic web.
  
## <a name="rtp-replay-attack"></a>Attaque par relecture RTP

Une attaque par relecture se produit lorsqu’une transmission multimédia valide entre deux correspondants est interceptée, puis retransmise à des fins malveillantes. L’utilisation de SRTP avec un protocole de signalisation sécurisé protège les transmissions contre les attaques par relecture. En effet, le destinataire est alors en mesure d’établir un index des paquets RTP déjà reçus et de comparer chaque nouveau paquet à ceux répertoriés dans l’index.
  
## <a name="spim"></a>Spim

Le spim correspond à des messages instantanés commerciaux ou des demandes d’abonnement aux informations de présence non sollicités. S’il ne constitue pas à lui seul une menace pour le réseau, il peut néanmoins perturber les activités des utilisateurs et avoir un impact négatif sur la disponibilité des ressources et la production. Il représente donc un risque potentiel pour le réseau. Prenons le cas d’utilisateurs qui génèrent du spim en s’envoyant mutuellement des demandes. Un utilisateur peut en bloquer un autre pour ne plus recevoir de messages instantanés indésirables. Toutefois, dans le cas de la fédération, il peut s’avérer difficile de faire face à une attaque de spim coordonnée, à moins de désactiver la fédération pour le partenaire.
  
## <a name="viruses-and-worms"></a>Virus et vers

Un virus est une unité de code dont le seul rôle consiste à reproduire d’autres unités de code similaires. Pour fonctionner, un virus doit être hébergé dans un fichier, un message électronique ou un programme. A qu’est une unité de code dont l’objectif est de reproduire des unités de code similaires supplémentaires, mais elle n’a pas besoin d’un hôte. Les virus et les vers apparaissent principalement lors du transfert de fichiers entre clients ou lorsque d’autres utilisateurs transmettent des URL. Une fois qu’un virus se trouve sur votre ordinateur, il peut, par exemple, usurper votre identité et envoyer des messages instantanés en votre nom.
  
## <a name="personally-identifiable-information"></a>Informations d’identification personnelle

Skype Entreprise Server peut divulguer des informations sur un réseau public qui peuvent être liées à un individu. Les types d’informations peuvent être décomposés en deux catégories spécifiques :
  
- **Données de présence améliorées** Les données de présence améliorées sont des informations qu’un utilisateur peut choisir de partager ou non sur un lien vers un partenaire fédéré ou avec des contacts au sein d’une organisation. Ces données ne sont pas partagées avec les utilisateurs sur un réseau de messagerie instantanée public. Les stratégies de client et d’autres configurations client peuvent placer un certain contrôle auprès de l’administrateur système. Dans Skype Entreprise Server, le mode de confidentialité améliorée de la présence peut être configuré pour un utilisateur individuel afin d’empêcher les utilisateurs Skype Entreprise qui ne sont pas sur la liste contacts de l’utilisateur de voir les informations de présence de l’utilisateur. Le mode de confidentialité améliorée de la présence n’empêche pas les utilisateurs de Microsoft Office Communicator 2007 et Microsoft Office Communicator 2007 R2 de voir les informations de présence d’un utilisateur. Pour plus d’informations sur le déploiement du client et de la présence, voir [Deploy clients for Skype Entreprise Server](../../deploy/deploy-clients/deploy-clients.md) and Plan for instant [messaging and presence in Skype Entreprise Server](../../plan-your-deployment/instant-messaging-and-presence.md).
    
- **Données obligatoires** Les données obligatoires sont requises pour le bon fonctionnement du serveur ou du client et ne sont PAS sous le contrôle de l’administration du client ou du système. Il s’agit des informations nécessaires au niveau du serveur ou du réseau à des fins de routage, de maintenance d’état et de signalisation.
    
Les tableaux suivants indiquent les données exposées sur un réseau public.
  
**Données de présence améliorées**

|**Données divulguées**|**Possibilités Paramètres**|
|:-----|:-----|
|Données personnelles  <br/> |Nom, Titre, Société, Adresse de messagerie, Fuseau horaire  <br/> |
|Numéros de téléphone  <br/> |Travail, Mobile, Domicile  <br/> |
|Informations de calendrier  <br/> |Informations de libre-service, d’informations sur l’out-of-town, de réunion (pour les personnes ayant accès à votre calendrier)  <br/> |
|Statut de présence  <br/> |Absent,Disponible, Occupé, Ne pas déranger, Hors connexion  <br/> |
   
**Données obligatoires**


| **Données divulguées** | **Exemple d’informations**                            |
|:-------------------|:---------------------------------------------------|
| Adresse IP  <br/>  | Adresse réelle de l’ordinateur ou adresse NATed  <br/> |
| URI SIP  <br/>     | jeremylos@litwareinc.com  <br/>                    |

