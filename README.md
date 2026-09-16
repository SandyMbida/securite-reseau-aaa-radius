# Sécurisation d’un réseau d’entreprise par AAA/RADIUS

## Présentation du projet

Ce projet porte sur le renforcement de la sécurité du système d’information du **Ministère des Postes et Télécommunications (MINPOSTEL)** par la mise en place d’une solution centralisée de contrôle d’accès réseau.

La solution repose sur le modèle **AAA (Authentication, Authorization and Accounting)** et le protocole **RADIUS**, associés au standard **IEEE 802.1X** et au protocole **EAP**.

L’objectif principal était de permettre l’authentification et l’autorisation des utilisateurs avant leur accès aux ressources du réseau.

---

## Objectifs

- Analyser les besoins de sécurité liés à l’accès au réseau.
- Mettre en place une authentification centralisée avec **RADIUS**.
- Intégrer le serveur RADIUS à **Active Directory**.
- Configurer le modèle **AAA** sur l’équipement réseau.
- Mettre en œuvre l’authentification réseau **IEEE 802.1X**.
- Utiliser les **VLAN** et les politiques réseau pour contrôler les accès.
- Tester les accès d’utilisateurs autorisés et non autorisés.
- Vérifier le fonctionnement de l’authentification à l’aide de **Wireshark**.

---

##  Technologies utilisées

| Technologie | Utilisation |
|---|---|
| Windows Server 2019 | Infrastructure serveur |
| Active Directory | Gestion centralisée des utilisateurs |
| Network Policy Server (NPS) | Serveur RADIUS |
| RADIUS | Authentification réseau centralisée |
| AAA | Authentification, autorisation et traçabilité |
| IEEE 802.1X | Contrôle d’accès au réseau |
| EAP | Mécanisme d’authentification |
| VLAN | Segmentation et contrôle d’accès |
| GNS3 | Simulation de l’infrastructure réseau |
| VirtualBox | Virtualisation |
| Wireshark | Analyse du trafic réseau |
| Windows 10 | Poste client |

---

##  Architecture de la solution

Le système repose sur une architecture d’authentification centralisée :

```text
Utilisateur / Windows 10
          │
          │ IEEE 802.1X
          ▼
   Commutateur réseau
     Client RADIUS
          │
          │ RADIUS
          ▼
 Windows Server 2019
      NPS / RADIUS
          │
          ▼
   Active Directory
