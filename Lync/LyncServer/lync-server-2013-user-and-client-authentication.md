---
title: Authentification utilisateur et client pour Lync Server 2013
TOCTitle: Authentification utilisateur et client pour Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59679141
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Authentification utilisateur et client pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-11-11_

Un utilisateur approuvé est un utilisateur dont les informations d’identification ont été authentifiées par un serveur approuvé dans Microsoft Lync Server 2013. Ce serveur est généralement un serveur serveur Standard Edition, Enterprise Editionserveur frontal ou directeur. Lync Server 2013 s’appuie sur services de domaine Active Directory comme référentiel principal unique approuvé des informations d’identification de l’utilisateur.

L’authentification consiste à fournir des informations d’identification d’utilisateur à un serveur approuvé. Lync Server 2013 utilise les protocoles d’authentification suivants, en fonction du statut et de l’emplacement de l’utilisateur.

  - **Protocole de sécurité MIT Kerberos version 5** pour utilisateurs internes avec informations d’identification Active Directory. Kerberos nécessite une connectivité client à services de domaine Active Directory, raison pour laquelle il ne peut pas être utilisé pour authentifier des clients externes au pare-feu d’entreprise.

  - **Protocole NTLM** pour utilisateurs avec informations d’identification Active Directory qui se connectent à partir d’un point de terminaison externe au pare-feu d’entreprise. Le service Edge d’accès transmet les demandes de connexion à un directeur, le cas échéant, ou à un serveur frontal pour authentification. Le service Edge d’accès lui-même n’effectue aucune authentification.
    
    > [!NOTE]  
    > Le protocole NTLM offre une protection plus faible contre les attaques que Kerberos, certaines organisations minimisent donc l’utilisation de NTLM. Par conséquent, l’accès à Lync Server 2013 peut être limité aux clients internes ou connectés via une connexion VPN ou DirectAccess.

  - **Protocole Digest** pour utilisateurs anonymes. Les utilisateurs anonymes sont des utilisateurs externes qui ne disposent pas d’informations d’identification Active Directory reconnues mais qui ont été invités à une conférence sur site et qui possèdent une clé de conférence valide. L’authentification Digest n’est pas utilisée pour d’autres interactions clients.

L’authentification Lync Server 2013 se compose de deux phases :

1.  Une association de sécurité est établie entre le client et le serveur.

2.  Le client et le serveur utilisent l’association de sécurité existante pour signer les messages qu’ils envoient et pour vérifier les messages qu’ils reçoivent. Les messages non authentifiés d’un client ne sont pas acceptés lorsque l’authentiffication est activée sur le serveur.

La confiance de l’utilisateur est associée à chaque message qui provient d’un utilisateur, et non à l’identité de l’utilisateur. Le serveur vérifie chaque message à la recherche d’informations d’identification d’utilisateur valides. Si les informations sont valides, le message est accepté non seulement par le premier serveur qui le reçoit mais par tous les autres serveurs dans le cloud de serveurs approuvés.

Les utilisateurs disposant d’informations d’identification valides émises par un partenaire fédéré sont approuvés mais peuvent éventuellement subir des contraintes supplémentaires les empêchant de profiter de la gamme complète de privilèges accordés aux utilisateurs internes.

Les protocoles ICE et TURN utilisent également le défi Digest tel que décrit dans le RFC TURN de l’IETF.

Les certificats clients offrent une méthode alternative aux utilisateurs pour s’authentifier auprès de Lync Server 2013. Au lieu de fournir un nom d’utilisateur et un mot de passe, les utilisateurs disposent d’un certificat et d’une clé privée correspondant au certificat requis pour résoudre un défi cryptographique. (Ce certificat doit comporter un nom d’objet ou un nom d’objet alternatif permettant d’identifier l’utilisateur et doit être émis par une CA racine approuvée par les serveurs exécutant Lync Server 2013, se trouver dans la période de validité du certificat et ne pas avoir été révoqué.) Pour être authentifiés, les utilisateurs doivent uniquement saisir un code confidentiel. Les certificats s’avèrent particulièrement utiles pour les téléphones et autres appareils exécutant Microsoft Lync 2013 Phone Edition où il est difficile de saisir un nom d’utilisateur et/ou un mot de passe.

